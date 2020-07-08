---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615679"
---
### <a name="certificate-eku-oid-validation"></a>EKU-OID-Zertifikatüberprüfung

#### <a name="details"></a>Details

Ab .NET Framework 4.6 führt die Klasse <xref:System.Net.Security.SslStream> oder <xref:System.Net.ServicePointManager> eine Überprüfung mithilfe der erweiterten Schlüsselverwendung (EKU) und unter Berücksichtigung von Objektbezeichnern (OIDs) durch. Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden. Bei der EKU-OID-Überprüfung werden Remotezertifikatrückrufe verwendet, um sicherzustellen, dass das Remotezertifikat über die richtigen OIDs für den entsprechenden Zweck verfügt.

#### <a name="suggestion"></a>Vorschlag

Wenn diese Änderung nicht erwünscht ist, können Sie die EKU-OID-Zertifikatüberprüfung deaktivieren, indem Sie die folgende Option [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Element Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt. Abgesehen davon wird die Verwendung nicht empfohlen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
