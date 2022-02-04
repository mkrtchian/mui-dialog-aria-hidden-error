# W3C validator error when opening a MUI Dialog

This repo has been bootstrapped with [MUI Create React App example with TypeScript](https://github.com/mui-org/material-ui/tree/master/examples/create-react-app-with-typescript).

It shows a code that results in an error about `<noscript>` tag having an `aria-hidden="true"` property when the dialog is open, which is not allowed.

The W3C validator gives the following error:

> Error: The aria-hidden attribute must not be specified on the noscript element.
