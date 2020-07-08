---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614540"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Die Standardalgorithmen SignedXML und SignedXMS wurden in SHA-256 geändert

#### <a name="details"></a>Details

In .NET Framework 4.7 und früheren Versionen verwenden SignedXML und SignedCMS für einige Vorgänge standardmäßig SHA-1. Ab .NET Framework 4.7.1 ist SHA-256 für diese Vorgänge standardmäßig aktiviert. Diese Änderung ist erforderlich, da SHA-1 nicht mehr sicher ist.

#### <a name="suggestion"></a>Vorschlag

Es gibt zwei neue Kontextwechselwerte, mit denen festgelegt wird, ob SHA-1 (unsicher) oder SHA-256 standardmäßig verwendet wird:

- Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms
- Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithmsBei Apps mit der Zielplattform .NET Framework 4.7.1 und höheren Versionen kann die Verwendung von SHA-1 als Standardoption wiederhergestellt werden, wenn die Verwendung von SHA-256 nicht erwünscht ist, indem die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzugefügt wird:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

Bei Apps mit der Zielplattform .NET Framework 4.7 und früheren Versionen können Sie sich für diese Änderung entscheiden, indem Sie die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
