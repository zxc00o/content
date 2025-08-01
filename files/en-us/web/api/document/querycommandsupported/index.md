---
title: "Document: queryCommandSupported() method"
short-title: queryCommandSupported()
slug: Web/API/Document/queryCommandSupported
page-type: web-api-instance-method
status:
  - deprecated
  - non-standard
browser-compat: api.Document.queryCommandSupported
---

{{ApiRef("DOM")}}{{deprecated_header}}{{Non-standard_header}}

> [!NOTE]
> Although the {{domxref("Document/execCommand", "execCommand()")}} method is deprecated, if you do decide to use it for reasons given on that page, you should consider checking the command's availability using `queryCommandSupported()` to ensure compatibility.

The **`Document.queryCommandSupported()`** method reports
whether or not the specified editor command is supported by the browser.

## Syntax

```js-nolint
queryCommandSupported(command)
```

### Parameters

- `command`
  - : The command for which to determine support.

### Return value

Returns a boolean value which is `true` if the command is supported
and `false` if the command isn't.

## Notes

The `'paste'` command return `false` not only if the feature is
unavailable, but also if the script calling it has insufficient privileges to perform
the action.

## Examples

```js
const flg = document.queryCommandSupported("SelectAll");

if (flg) {
  // Do something…
}
```

## Specifications

This feature is not part of any current specification. It is no longer on track to become a standard. There is an unofficial [W3C execCommand spec draft](https://w3c.github.io/editing/docs/execCommand/).

## Browser compatibility

{{Compat}}

## See also

- {{domxref("document.execCommand()")}}
- {{domxref("document.queryCommandEnabled()")}}
