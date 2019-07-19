---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802646"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM hat die ByRef-SafeArray-Parameter für Ereignisse erfolgreich gemarshallt.

|   |   |
|---|---|
|Details|In .NET Framework 4.7.2 und früheren Version konnte der ByRef-[SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter für ein COM-Ereignis nicht wieder in nativen Code gemarshallt werden.  Durch diese Änderung der [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter wieder erfolgreich gemarshallt.<ul><li>[X] Quirking</li></ul>|
|Vorschlag|Wenn ein ordnungsgemäßes Marshalling des ByRef-SafeArray-Parameters bei COM-Ereignissen die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfigurationsoption Ihrer Anwendungskonfiguration hinzufügen:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.8|
|Typ|Laufzeit|

