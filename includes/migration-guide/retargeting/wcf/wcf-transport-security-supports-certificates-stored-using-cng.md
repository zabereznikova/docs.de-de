---
ms.openlocfilehash: b57e0acb03a99f33460a7b6c880280b37e01a17b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859299"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden

|   |   |
|---|---|
|Details|Von Apps für die Zielplattform .NET Framework 4.6.2 an unterstützt WCF-Transportsicherheit Zertifikate, die mithilfe der Windows-Kryptographiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn eine Anwendung auf .NET Framework 4.6.2 ausgerichtet ist, ist dieses Feature standardmäßig aktiviert. In früheren Versionen von .NET Framework löst der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicheranbieter zu verwenden, eine Ausnahme aus.|
|Vorschlag|Apps für die Zielplattform .NET Framework 4.6.1 und früher, die unter .NET Framework 4.6.2 ausgeführt werden, können Unterstützung für CNG-Zertifikate aktivieren, indem sie dem <code>&lt;runtime&gt;</code>-Abschnitt der app.config- oder der web.config-Datei die folgende Zeile hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Dies kann mithilfe des folgenden Codes auch programmgesteuert erfolgen:<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Beachten Sie, dass aufgrund dieser Änderung jeglicher Code zur Ausnahmebehandlung, der von dem Versuch zur Einleitung von sicherer Kommunikation mit einem CNG-Zertifikat abhängt, nicht ausgeführt wird.|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
