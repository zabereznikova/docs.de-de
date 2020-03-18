---
ms.openlocfilehash: db076d6799e4de5b8610cf9c1aac79b5386a7229
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859037"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Die Standardalgorithmen SignedXML und SignedXMS wurden in SHA-256 geändert

|   |   |
|---|---|
|Details|In .NET Framework 4.7 und früheren Versionen verwenden SignedXML und SignedCMS für einige Vorgänge standardmäßig SHA-1. Ab .NET Framework 4.7.1 ist SHA-256 für diese Vorgänge standardmäßig aktiviert. Diese Änderung ist erforderlich, da SHA-1 nicht mehr sicher ist.|
|Vorschlag|Es gibt zwei neue Kontextwechselwerte, mit denen festgelegt wird, ob SHA-1 (unsicher) oder SHA-256 standardmäßig verwendet wird:<ul><li>Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</li><li>Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms</li></ul>Bei Apps mit der Zielplattform .NET Framework 4.7.1 und höheren Versionen kann die Verwendung von SHA-1 als Standardoption wiederhergestellt werden, wenn die Verwendung von SHA-256 nicht erwünscht ist, indem die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzugefügt wird:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true&quot; /&gt;&#13;&#10;</code></pre>Bei Apps mit der Zielplattform .NET Framework 4.7 und früheren Versionen können Sie sich für diese Änderung entscheiden, indem Sie die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false&quot; /&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType></li></ul>|
