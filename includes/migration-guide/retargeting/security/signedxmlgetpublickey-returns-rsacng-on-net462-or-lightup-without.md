---
ms.openlocfilehash: cdcf7f540a9ded4108121b2cd8e855687a0c7e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858923"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey gibt unter .NET Framework 4.6.2 RSACng (oder CngLightup) zurück, ohne Änderungen neu zuzuweisen

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 wird für den konkreten Typ des Objekts, das von der <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>-Methode zurückgegeben wird, nicht mehr die CryptoServiceProvider-Implementierung, sondern eine Cng-Implementierung verwendet. Probleme sind durch diese Änderung nicht aufgetreten. Der Grund für die Änderung ist, dass für die Implementierung anstelle von <code>certificate.PublicKey.Key</code> nun die interne Methode <code>certificate.GetAnyPublicKey</code> verwendet wird, die eine Weiterleitung zu <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType> vornimmt.|
|Vorschlag|Für Apps, die unter .NET Framework 4.7.1 oder einer neueren Version ausgeführt werden, können Sie die standardmäßig von .NET Framework 4.6.1 und früheren Versionen verwendete CryptoServiceProvider-Implementierung verwenden, indem Sie dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei die folgende Konfigurationsoption hinzufügen:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true&quot; /&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType></li></ul>|
