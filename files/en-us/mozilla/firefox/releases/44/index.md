---
title: Firefox 44 for developers
short-title: Firefox 44
slug: Mozilla/Firefox/Releases/44
page-type: firefox-release-notes
sidebar: firefox
---

[To test the latest developer features of Firefox, install Firefox Developer Edition](https://www.firefox.com/en-US/channel/desktop/developer/).
Firefox 44 was released on January 26, 2016. This article lists key changes that are useful not only for web developers, but also Firefox and Gecko developers as well as add-on developers.

## Changes for Web developers

### Developer tools

Highlights:

- [Memory tool](https://firefox-source-docs.mozilla.org/devtools-user/memory/index.html)
- [Animation inspector improvements](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/work_with_animations/index.html)
- [New Waterfall markers: DomContentLoaded, load, worker messages](https://web.archive.org/web/20211207010020/https://firefox-source-docs.mozilla.org/devtools-user/performance/waterfall/index.html#markers)

[All devtools bugs fixed between Firefox 43 and Firefox 44.](https://bugzilla.mozilla.org/buglist.cgi?resolution=FIXED&classification=Client%20Software&chfieldto=2015-11-03&query_format=advanced&chfield=resolution&chfieldfrom=2015-09-19&chfieldvalue=FIXED&bug_status=RESOLVED&bug_status=VERIFIED&component=Developer%20Tools&component=Developer%20Tools%3A%203D%20View&component=Developer%20Tools%3A%20Canvas%20Debugger&component=Developer%20Tools%3A%20Console&component=Developer%20Tools%3A%20Debugger&component=Developer%20Tools%3A%20Framework&component=Developer%20Tools%3A%20Graphic%20Commandline%20and%20Toolbar&component=Developer%20Tools%3A%20Inspector&component=Developer%20Tools%3A%20Memory&component=Developer%20Tools%3A%20Netmonitor&component=Developer%20Tools%3A%20Object%20Inspector&component=Developer%20Tools%3A%20Performance%20Tools%20%28Profiler%2FTimeline%29&component=Developer%20Tools%3A%20Responsive%20Mode&component=Developer%20Tools%3A%20Scratchpad&component=Developer%20Tools%3A%20Source%20Editor&component=Developer%20Tools%3A%20Storage%20Inspector&component=Developer%20Tools%3A%20Style%20Editor&component=Developer%20Tools%3A%20User%20Stories&component=Developer%20Tools%3A%20Web%20Audio%20Editor&component=Developer%20Tools%3A%20WebGL%20Shader%20Editor&component=Developer%20Tools%3A%20WebIDE&product=Firefox&list_id=12582678)

### HTML

- [`<link rel="prefetch">`](/en-US/docs/Glossary/Prefetch) now obeys the [`crossorigin`](/en-US/docs/Web/HTML/Reference/Elements/link#crossorigin) attribute ([Firefox bug 1214819](https://bugzil.la/1214819)).

### CSS

- `position: fixed;` now always creates a new stacking context ([Firefox bug 1179288](https://bugzil.la/1179288)).
- The support of {{cssxref('@font-face/unicode-range', 'unicode-range')}} has been enabled by default ([Firefox bug 1119062](https://bugzil.la/1119062)).
- Our experimental implementation of CSS Writing Modes has been updated to reflect the latest specification:
  - The value `sideways` of the {{cssxref("text-orientation")}} property has been implemented and `sideways-right` has been made an alias of it ([Firefox bug 1193488](https://bugzil.la/1193488)).
  - The value `sideways-rl` and `sideways-lr` of the {{cssxref("writing-mode")}} property ([Firefox bug 1193488](https://bugzil.la/1193488) and [Firefox bug 1193519](https://bugzil.la/1193519)).

- The non-standard properties `-moz-math-display` and `-moz-window-shadow` are no more available from Web content ([Firefox bug 1207002](https://bugzil.la/1207002), [Firefox bug 1211040](https://bugzil.la/1211040), and [Firefox bug 1212607](https://bugzil.la/1212607)).
- The {{cssxref("font-style")}} property now distinguishes between `oblique` and `italic` when both variants are available ([Firefox bug 543715](https://bugzil.la/543715)).
- Though not supported, the properties {{cssxref("@page/marks", "marks")}}, {{cssxref("orphans")}}, {{cssxref("page")}}, {{cssxref("@page/size", "size")}}, and {{cssxref("widows")}}, were parsed and {{cssxref("@supports")}} was incorrectly reporting them as supported; this has been fixed and the properties are not parsed anymore, nor marked as supported ([Firefox bug 1215702](https://bugzil.la/1215702)).
- The internal value `-moz-mac-unified-toolbar` has been removed from the possible values for the {{cssxref("appearance")}} property ([Firefox bug 1206468](https://bugzil.la/1206468)).
- Several `-webkit` prefixed properties and values have been added for web compatibility, behind the preference `layout.css.prefixes.webkit`, defaulting to `false` ([Firefox bug 837211](https://bugzil.la/837211)):
  - `-webkit-animation`
  - `-webkit-animation-delay`
  - `-webkit-animation-direction`
  - `-webkit-animation-duration`
  - `-webkit-animation-fill-mode`
  - `-webkit-animation-iteration-count`
  - `-webkit-animation-name`
  - `-webkit-animation-play-state`
  - `-webkit-animation-timing-function`
  - `-webkit-text-size-adjust`
  - `-webkit-transform`
  - `-webkit-transform-origin`
  - `-webkit-transform-style`
  - `-webkit-transition`
  - `-webkit-transition-delay`
  - `-webkit-transition-duration`
  - `-webkit-transition-property`
  - `-webkit-transition-timing-function`
  - `-webkit-border-radius`
  - `-webkit-border-top-left-radius`
  - `-webkit-border-top-right-radius`
  - `-webkit-border-bottom-left-radius`
  - `-webkit-border-bottom-right-radius`
  - `-webkit-appearance`
  - `-webkit-background-clip`
  - `-webkit-background-origin`
  - `-webkit-background-size`
  - `-webkit-border-image`
  - `-webkit-box-shadow`
  - `-webkit-box-sizing`
  - `-webkit-user-select`
  - `-webkit-linear-gradient()` [Firefox bug 1210575](https://bugzil.la/1210575)
  - `-webkit-radial-gradient"()` [Firefox bug 1210575](https://bugzil.la/1210575)
  - `-webkit-repeating-linear-gradient()` [Firefox bug 1210575](https://bugzil.la/1210575)
  - `-webkit-repeating-radial-gradient()` [Firefox bug 1210575](https://bugzil.la/1210575)

### JavaScript

#### New APIs

- {{jsxref("Symbol.toPrimitive")}}, [`Symbol.prototype[Symbol.toPrimitive]()`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/Symbol.toPrimitive), and [`Date.prototype[Symbol.toPrimitive]()`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Symbol.toPrimitive) have been implemented ([Firefox bug 1054756](https://bugzil.la/1054756)).

#### Changes

- The [`let`](/en-US/docs/Web/JavaScript/Reference/Statements/let) and [`const`](/en-US/docs/Web/JavaScript/Reference/Statements/const) bindings in the global level have been made compliant with ES2015 semantics. See [Firefox bug 589199](https://bugzil.la/589199) and the blog post ["Breaking changes in let and const in Firefox Nightly 44"](https://blog.mozilla.org/addons/2015/10/14/breaking-changes-let-const-firefox-nightly-44/). In addition, `let` is now available to default Web JavaScript (strict and non-strict) and does not require a version opt-in anymore ([Firefox bug 932517](https://bugzil.la/932517)).
- If [typed arrays'](/en-US/docs/Web/JavaScript/Guide/Typed_arrays) (like {{jsxref("Int8Array", "Int8Array")}}) and {{jsxref("ArrayBuffer", "ArrayBuffer")}}) constructors are called as a function without the {{jsxref("Operators/new", "new")}} operator, a {{jsxref("TypeError")}} is now thrown as per the ES2015 specification ([Firefox bug 980945](https://bugzil.la/980945), [Firefox bug 1214936](https://bugzil.la/1214936)).
- The {{jsxref("RegExp")}} sticky flag now follows the ES2015 standard for [anchored sticky regular expressions](/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky#anchored_sticky_flag) ([Firefox bug 773687](https://bugzil.la/773687)).
- The JavaScript shell (SpiderMonkey's REPL) now defaults to the default, Web-compatible JS version (and not JS1.7+ anymore) ([Firefox bug 1192329](https://bugzil.la/1192329)).

#### Removals

- Support for the non-standard [`let` blocks](/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#statements_2) has been dropped ([Firefox bug 1167029](https://bugzil.la/1167029).
- The non-standard and deprecated property `Object.prototype.__noSuchMethod__` has been removed ([Firefox bug 683218](https://bugzil.la/683218)).

### Interfaces/APIs/DOM

#### DOM & HTML DOM

- For compatibility with specific existing sites, the property `Document.charset` has been implemented as an alias of {{domxref("Document.characterSet")}} ([Firefox bug 647621](https://bugzil.la/647621)).
- Support for the `window.sidebar.addSearchEngine()` method, which allowed Web pages to invoke an installation of a Sherlock plugin, has been dropped and now it just logs a warning in the Web Console ([Firefox bug 862148](https://bugzil.la/862148)).
- To fight unwanted pop-ups, prompts requested in {{domxref("Window/beforeunload_event", "beforeunload")}} events of pages that have not been interacted with are no more displayed ([Firefox bug 636905](https://bugzil.la/636905)).
- The deprecated method {{domxref("MessageEvent.initMessageEvent()")}} has been reimplemented for backward compatibility ([Firefox bug 949376](https://bugzil.la/949376)).
- The obsolete property `DocumentType.internalSubset` has been removed ([Firefox bug 801545](https://bugzil.la/801545)).
- For compatibility with existing sites, the {{domxref("Window.orientation")}} property and the {{domxref("Window.orientationchange_event", "orientationchange")}} event have been implemented ([Firefox bug 920734](https://bugzil.la/920734)).
- An {{HTMLElement("iframe")}} with explicit fullscreen request should not exit fullscreen implicitly ([Firefox bug 1187801](https://bugzil.la/1187801)).
- The events {{domxref("Element/mouseover_event", "mouseover")}}, {{domxref("Element/mouseout_event", "mouseout")}}, {{domxref("Element/mouseenter_event", "mouseenter")}}, {{domxref("Element/mouseleave_event", "mouseleave")}}, {{domxref("Element/pointermove_event", "pointermove")}}, {{domxref("Element/pointerover_event", "pointerover")}}, {{domxref("Element/pointerout_event", "pointerout")}}, {{domxref("Element/pointerenter_event", "pointerenter")}} and {{domxref("Element/pointerleave_event", "pointerleave")}} are now triggered for disabled form elements ([Firefox bug 218093](https://bugzil.la/218093)).
- The method {{domxref("Element/matches", "Element.webkitMatchesSelector()")}} has been added ([Firefox bug 1216193](https://bugzil.la/1216193)) to improve interoperability.
- To match the spec, the method {{domxref("Document.createAttribute()")}} now converts the input to lower case ([Firefox bug 1176313](https://bugzil.la/1176313)).
- The non-standard `dialog` feature for {{domxref("Window.open()")}} is no longer available to Web content. It is still available to extensions and other code with chrome privileges ([Firefox bug 1095236](https://bugzil.la/1095236).

#### Canvas

- A new experimental {{domxref("OffscreenCanvas")}} API that allows rendering contexts (such as [WebGL](/en-US/docs/Web/API/WebGL_API)) to run in [Web Workers](/en-US/docs/Web/API/Web_Workers_API) has been implemented. To use this experimental API set `gfx.offscreencanvas.enabled` to `true` in about:config ([Firefox bug 709490](https://bugzil.la/709490)). This API includes:
  - The {{domxref("OffscreenCanvas")}} interface,
  - {{domxref("HTMLCanvasElement.transferControlToOffscreen()")}}, and
  - `WebGLRenderingContext.commit()`.
  - Several WebGL interfaces are now also available in a worker context when this API is enabled.

#### WebGL

- Uniform Buffer Objects have been implemented ([Firefox bug 1048747](https://bugzil.la/1048747)).

#### IndexedDB

- The {{domxref("IDBIndex.getAll()")}} and {{domxref("IDBIndex.getAllKeys()")}}, and there counterparts on {{domxref("IDBObjectStore")}} are now available by default ([Firefox bug 1196841](https://bugzil.la/1196841)).

#### Service Workers

- The `ServiceWorkerMessageEvent` and {{domxref("ExtendableMessageEvent")}} interfaces have been implemented ([Firefox bug 1143717](https://bugzil.la/1143717) and [Firefox bug 1207068](https://bugzil.la/1207068)).
- {{domxref("Headers")}} objects now support a pair iterator, meaning that the methods {{domxref("Headers.entries()")}}, {{domxref("Headers.keys()")}}, and {{domxref("Headers.values()")}} are now available; {{jsxref("Symbol.iterator")}} now also returns the default iterator for them ([Firefox bug 1108181](https://bugzil.la/1108181)).
- The {{domxref('XMLHttpRequest')}} API has been disabled on Service Workers ([Firefox bug 931243](https://bugzil.la/931243)).
- The interface {{domxref("FetchEvent")}} now extends {{domxref("ExtendableEvent")}}, giving it access to the {{domxref("ExtendableEvent.waitUntil()")}} method. ([Firefox bug 1214772](https://bugzil.la/1214772)).
- Following a recent change in the specification, `FetchEvent.client` has been removed ([Firefox bug 1218135](https://bugzil.la/1218135)).
- To match the latest specification, the `ServiceWorkerContainer.onreloadpage` has been removed ([Firefox bug 1218139](https://bugzil.la/1218139)).
- The event handlers `ServiceWorkerGlobalScope.onbeforeevicted` and `ServiceWorkerGlobalScope.onevicted` have been removed as they weren't following the spec. They will be reintroduced in the future, but their removal will allow feature detection to work as expected ([Firefox bug 1218142](https://bugzil.la/1218142)).
- In the {{domxref("FetchEvent.FetchEvent", "FetchEvent()")}} constructor, if the `isReload` member is not present in the options dictionary, it now defaults to `false` ([Firefox bug 1216401](https://bugzil.la/1216401)).
- The {{domxref("Client.frameType")}} property is now implemented on the right interface; it was on {{domxref("WindowClient")}} before ([Firefox bug 1218146](https://bugzil.la/1218146)).
- When AppCache is used to provide offline support for a page, a warning message is now displayed in the console advising developers to use [Service workers](/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers) instead ([Firefox bug 1204581](https://bugzil.la/1204581).)
- Service workers have been enabled by default in Gecko.

#### WebRTC

- WebRTC interfaces have been _unprefixed_ ([Firefox bug 1155923](https://bugzil.la/1155923)). In particular:
  - `mozRTCPeerConnection` is now {{domxref("RTCPeerConnection")}}.
  - `mozRTCIceCandidate` is now {{domxref("RTCIceCandidate")}}.
  - `mozRTCSessionDescription` is now {{domxref("RTCSessionDescription")}}.

- The {{domxref("RTCDataChannel.bufferedAmountLowThreshold")}} property, as well as the {{domxref("RTCDataChannel.bufferedamountlow_event", "bufferedamountlow")}} event and its event handler, have been implemented ([Firefox bug 1178091](https://bugzil.la/1178091)).
- The attribute {{domxref("RTCPeerConnection.canTrickleIceCandidates")}} has been added, the non-standard method `RTCPeerConnection.updateIce()` removed ([Firefox bug 1209744](https://bugzil.la/1209744)).
- The {{domxref("MediaStream")}} interface now supports the {{domxref("MediaStream.addTrack()")}} and {{domxref("MediaStream.removeTrack()")}} methods ([Firefox bug 1103188](https://bugzil.la/1103188)).
- The constructor {{domxref("MediaStream.MediaStream", "MediaStream()")}} has been implemented ([Firefox bug 1070216](https://bugzil.la/1070216)).
- Support for the non-standard constraint style option list for `RTCOfferOptions` has been removed.

#### New APIs

- An experimental implementation of the Canvas API in Workers has landed: {{domxref("OffscreenCanvas")}} and {{domxref("HTMLCanvasElement.transferControlToOffscreen()")}} are available behind the `gfx.offscreencanvas.enabled` preference, currently disabled by default ([Firefox bug 709490](https://bugzil.la/709490)).
- The Text2Speech API, part of Web Speech API, has now an OS X backend. But this is disabled by default ([Firefox bug 1003452](https://bugzil.la/1003452)).

#### Miscellaneous

- {{domxref("URLSearchParams")}} objects now support a pair iterator, meaning that the methods {{domxref("URLSearchParams.entries()")}}, {{domxref("URLSearchParams.keys()")}}, and {{domxref("URLSearchParams.values()")}} are now available; {{jsxref("Symbol.iterator")}} now also returns the default iterator for them ([Firefox bug 1085284](https://bugzil.la/1085284)).
- {{domxref("FormData")}} objects now support a pair iterator, meaning that the methods {{domxref("FormData.entries()")}}, {{domxref("FormData.keys")}}, and {{domxref("FormData.values()")}} are now available; {{jsxref("Symbol.iterator")}} now also returns the default iterator for them ([Firefox bug 1127703](https://bugzil.la/1127703)).
- When {{domxref("XMLHttpRequest.send()")}} is used with an HTML document, it now uses `text/html` instead of `application/xml` ([Firefox bug 918771](https://bugzil.la/918771)).
- Speech synthesis (text-to-speech) has been implemented in Firefox Desktop for Mac and Linux, hidden behind the `media.webspeech.synth.enabled` flag in `about:config` ([Firefox bug 1003452](https://bugzil.la/1003452), [Firefox bug 1003464](https://bugzil.la/1003464).) See [Web Speech API](/en-US/docs/Web/API/Web_Speech_API) for more information.
- Elements inside a {{HTMLElement("frame")}} or an {{HTMLElement('object')}} can't be set fullscreen anymore ([Firefox bug 1212299](https://bugzil.la/1212299)).
- Sanitization of WOFF fonts is a bit more stricter, leading to more incorrect fonts being rejected, this sanitization is made a bit less stricter in Firefox 46 ([Firefox bug 1193050](https://bugzil.la/1193050) and [Firefox bug 1244693](https://bugzil.la/1244693)).

### MathML

_No change._

### SVG

_No change._

### Audio/Video

_No change._

## HTTP

- Support for the [Brotli](https://en.wikipedia.org/wiki/Brotli) algorithm has been added and both [`Accept-Encoding`](/en-US/docs/Web/HTTP/Guides/Content_negotiation#the_accept-encoding_header) and [`Content-Encoding`](/en-US/docs/Web/HTTP/Reference/Headers/Content-Encoding) headers now support the `br` value ([Firefox bug 366559](https://bugzil.la/366559) and [Firefox bug 1211916](https://bugzil.la/1211916)).
- Incorrect support of HTTP/2 headers containing line breaks (`'/n'`) have been removed as the spec doesn't allow it, unlike HTTP/1 ([Firefox bug 1197847](https://bugzil.la/1197847)).

## Networking

_No change._

## Security

- RC4 is now also disabled by default on Beta and Release versions of the browser ([Firefox bug 1201025](https://bugzil.la/1201025)) and the whitelist is now empty by default ([Firefox bug 1215796](https://bugzil.la/1215796)).

## Changes for add-on and Mozilla developers

### Interfaces

_No change._

### XUL

_No change._

### JavaScript code modules

- Added `LIKE` support to Sqlite.jsm ([Firefox bug 1188760](https://bugzil.la/1188760)).
- Added [Snackbars.jsm](https://web.archive.org/web/20160423072423/https://developer.mozilla.org/en-US/Add-ons/Firefox_for_Android/API/Snackbars.jsm) module to [Firefox for Android](https://web.archive.org/web/20210518020027/https://developer.mozilla.org/en-US/docs/Mozilla/Firefox_for_Android) ([Firefox bug 1215026](https://bugzil.la/1215026))

### XPCOM

- The `nsIDOMWindow` interface is now empty. Its contents were either no longer used, had moved elsewhere, or were only used from C++. The items available from C++ code now reside in the [nsPIDOMWindow](https://searchfox.org/mozilla-central/source/dom/base/nsPIDOMWindow.h) interface ([Firefox bug 1216401](https://bugzil.la/1216401)).

### Other

- Due to breaking changes in Firefox 44 ([bug 1202902](https://bugzil.la/1202902)), add-ons packed with [cfx](https://web.archive.org/web/20201201072958/https://developer.mozilla.org/en-US/docs/Archive/Add-ons/Add-on_SDK/Tools/cfx) will not work any longer. To make your add-on compatible again, please use [jpm](https://web.archive.org/web/20210221222338/https://developer.mozilla.org/en-US/docs/Archive/Add-ons/Add-on_SDK/Tools/jpm). See the [_cfx_ to _jpm_ migration guide](https://web.archive.org/web/20181116093809/https://developer.mozilla.org/en-US/docs/Archive/Add-ons/Add-on_SDK/Tools/cfx_to_jpm).
