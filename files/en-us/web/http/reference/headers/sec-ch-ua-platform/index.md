---
title: Sec-CH-UA-Platform header
short-title: Sec-CH-UA-Platform
slug: Web/HTTP/Reference/Headers/Sec-CH-UA-Platform
page-type: http-header
status:
  - experimental
browser-compat: http.headers.Sec-CH-UA-Platform
sidebar: http
---

{{SeeCompatTable}}{{SecureContext_Header}}

The HTTP **`Sec-CH-UA-Platform`** {{Glossary("request header")}} is a [user agent client hint](/en-US/docs/Web/HTTP/Guides/Client_hints#user_agent_client_hints) which provides the platform or operating system on which the user agent is running.
For example: "Windows" or "Android".

`Sec-CH-UA-Platform` is a [low entropy hint](/en-US/docs/Web/HTTP/Guides/Client_hints#low_entropy_hints).
Unless blocked by a user agent permission policy, it is sent by default (without the server opting in by sending {{HTTPHeader("Accept-CH")}}).

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Header type</th>
      <td>
        {{Glossary("Request header")}},
        <a href="/en-US/docs/Web/HTTP/Guides/Client_hints">Client hint</a>
      </td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Forbidden request header")}}</th>
      <td>Yes (<code>Sec-</code> prefix)</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Sec-CH-UA-Platform: <platform>
```

### Directives

- `<platform>`
  - : One of the following strings: `"Android"`, `"Chrome OS"`, `"Chromium OS"`, `"iOS"`, `"Linux"`, `"macOS"`, `"Windows"`, or `"Unknown"`.

## Examples

### Using Sec-CH-UA-Platform

As `Sec-CH-UA-Platform` is a [low entropy hint](/en-US/docs/Web/HTTP/Guides/Client_hints#low_entropy_hints) it is typically sent in all requests.
A browser running on a macOS computer might add the following header to all requests.

```http
Sec-CH-UA-Platform: "macOS"
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Client hints](/en-US/docs/Web/HTTP/Guides/Client_hints)
- [User-Agent Client Hints API](/en-US/docs/Web/API/User-Agent_Client_Hints_API)
- {{HTTPHeader("Accept-CH")}}
- [HTTP Caching: Vary](/en-US/docs/Web/HTTP/Guides/Caching#vary) and {{HTTPHeader("Vary")}} header
- [Improving user privacy and developer experience with User-Agent Client Hints](https://developer.chrome.com/docs/privacy-security/user-agent-client-hints) (developer.chrome.com)
