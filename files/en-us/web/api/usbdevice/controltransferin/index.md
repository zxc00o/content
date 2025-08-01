---
title: "USBDevice: controlTransferIn() method"
short-title: controlTransferIn()
slug: Web/API/USBDevice/controlTransferIn
page-type: web-api-instance-method
status:
  - experimental
browser-compat: api.USBDevice.controlTransferIn
---

{{APIRef("WebUSB API")}}{{SeeCompatTable}}{{SecureContext_Header}}{{AvailableInWorkers}}

The **`controlTransferIn()`** method of the {{domxref("USBDevice")}} interface returns a {{jsxref("Promise")}} that resolves with a {{domxref("USBInTransferResult")}} when a command or status request has been transmitted to (received by) the USB device.

## Syntax

```js-nolint
controlTransferIn(setup, length)
```

### Parameters

- `setup`
  - : An object that sets options for. The available options are:
    - `requestType`
      - : Must be one of three values specifying whether the transfer is `"standard"` (common to all USB devices) `"class"` (common to an industry-standard class of devices) or `"vendor"`.
    - `recipient`
      - : Specifies the target of the transfer on the device, one of `"device"`, `"interface"`, `"endpoint"`, or `"other"`.
    - `request`
      - : A vendor-specific command.
    - `value`
      - : Vendor-specific request parameters.
    - `index`
      - : The interface number of the recipient.

- `length`
  - : The maximum number of bytes to read from the device. The actual data is in the {{domxref("USBInTransferResult")}} in the resolved Promise.

### Return value

{{jsxref("promise")}} that resolves with a {{domxref("USBInTransferResult")}}.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
