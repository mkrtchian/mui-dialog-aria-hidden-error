# W3C validator error with MUI Dialog and aria-hidden

This repo has been bootstrapped with [MUI Create React App example with TypeScript](https://github.com/mui-org/material-ui/tree/master/examples/create-react-app-with-typescript).

It shows a code that results in errors about some HTML tags having an invalid `aria-hidden="true"` attribute when the dialog is opened.

## Erroring tags in this app

The full list of the HTML elements that can't have `aria-hidden` can be found in the [html-aria website](https://www.w3.org/TR/html-aria/#docconformance).

This app contains the ones that may be direct children of the `<body>` tag, and therefore get the `aria-hidden` attribute:

- `<input type="hidden">`
- `<link>`
- `<map>`
- `<meta>`
- `<noscript>`
- `<picture>`
- `<script>`
- `<template>`

The following ones can't be direct children of body :

- `<base>`: can only be used in `<head>`
- `<col>` and `<colgroup>`: can only be used in a `<table>`, so can't be direct child of `<body>`
- `<head>`: can't be direct child of `<body>`
- `<html>`: can't be direct child of `<body>`
- `<param>`: has to be direct child of `<object>`, so can't be direct child of `<body>`
- `<slot>`: has to be used in phrasing content, so can't be direct child of `<body>` that has flow content
- `<source>`: has to be a direct child of `<picture>` or a media element, so can't be direct child of `<body>`
- `<style>`: has to be in the `<head>` or in a meta contaxt, so can't be direct child of `<body>`
- `<title>`: has to be a direct child of `<head>`, so can't be direct child of `<body>`
- `<track>`: has to be a child of a media element, so can't be direct child of `<body>`

## Currently errors with the validator

> Error: The aria-hidden attribute must not be specified on an input element whose type attribute has the value hidden.

> Error: The aria-hidden attribute must not be specified on the link element.

> Error: The aria-hidden attribute must not be specified on the map element.

> Error: The aria-hidden attribute must not be specified on the meta element.

> Error: The aria-hidden attribute must not be specified on the noscript element.

> Error: The aria-hidden attribute must not be specified on the picture element.
