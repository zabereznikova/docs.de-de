---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497862"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM hat die ByRef-SafeArray-Parameter für Ereignisse erfolgreich gemarshallt.

#### <a name="details"></a>Details

In .NET Framework 4.7.2 und früheren Version konnte der ByRef-[SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter für ein COM-Ereignis nicht wieder in nativen Code gemarshallt werden.  Durch diese Änderung der [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter wieder erfolgreich gemarshallt.<ul><li>[X] Quirking</li></ul>

#### <a name="suggestion"></a>Vorschlag

Wenn ein ordnungsgemäßes Marshalling des ByRef-SafeArray-Parameters bei COM-Ereignissen die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfigurationsoption Ihrer Anwendungskonfiguration hinzufügen:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.8|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
