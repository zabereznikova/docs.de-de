---
ms.openlocfilehash: 6ff23bbe8c48235770d39cb7d35a1df7de6c5201
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68440266"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM hat die ByRef-SafeArray-Parameter für Ereignisse erfolgreich gemarshallt.

|   |   |
|---|---|
|Details|In .NET Framework 4.7.2 und früheren Version konnte der ByRef-[SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter für ein COM-Ereignis nicht wieder in nativen Code gemarshallt werden.  Durch diese Änderung der [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter wieder erfolgreich gemarshallt.<ul><li>[X] Quirking</li></ul>|
|Vorschlag|Wenn ein ordnungsgemäßes Marshalling des ByRef-SafeArray-Parameters bei COM-Ereignissen die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfigurationsoption Ihrer Anwendungskonfiguration hinzufügen:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.8|
|Geben Sie Folgendes ein:|Laufzeit|
