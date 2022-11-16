# super-react-dialog

Simple declarative API for rendering Material UI Dialogs written in TypeScript

## Motivation

`super-react-dialog` was written while building a learning portal website. With around ~15 unique Dialogs, it became obvious that many of the dialogs shared much of the same structure and that we could configure and reuse the same components through a single extensible API.

## Installation

```bash
npm install super-react-dialog --save
```

**Note:** super-react-dialog (as the name suggests) assumes that you're using react, specifically version >= 16.8, and mui.

## Getting Started

In a nutshell there are 3 objects to know about.

- `DialogProvider` - to be included near the root of the tree.
- `useDialog` - the hook associated with the provider.
- `openDialog` - The function which will configure, open, and handle the dialog.

To start, wrap your app (or some part of the subtree) in the provider, something like:

```jsx
// file: App.tsx
import * as React from "react";

import { DialogProvider } from "super-react-dialog";
import { ThemeProvider } from "@mui/material";

// ...

export const App = () => {
  // ...

  return (
    <ThemeProvider>
      <DialogProvider>
        {/*  ----------  other components  ----------  */}
      </DialogProvider>
    </ThemeProvider>
  );
};