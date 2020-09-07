---
ms.openlocfilehash: c8f017084fc1ec1eca636ef0178a40559e15b2c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497094"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a>Verbesserte WCF-Zertifikatkettenüberprüfung für die Net.Tcp-Zertifikatauthentifizierung

#### <a name="details"></a>Details

.NET Framework 4.7.2 verbessert die Zertifikatkettenüberprüfung, wenn Zertifikatauthentifizierung mit Transportsicherheit mit WCF verwendet wird. Durch diese Verbesserung müssen Clientzertifikate, die verwendet werden, um die Authentifizierung mit einem Server auszuführen, für Clientauthentifizierung konfiguriert werden.  Entsprechend müssen auch Serverzertifikate, die zur Authentifizierung eines Servers dienen, für Serverauthentifizierung konfiguriert werden. Wenn das Stammzertifikat deaktiviert ist, schlägt die Überprüfung der Zertifikatkette aufgrund dieser Änderung fehl. Für .NET Framework 3.5 und höhere Versionen wurde über das Windows-Sicherheitsrollup die gleiche Änderung vorgenommen. Weitere Informationen finden Sie [hier](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Diese Änderung ist standardmäßig aktiviert und kann durch eine Konfigurationseinstellung deaktiviert werden.

#### <a name="suggestion"></a>Vorschlag

<ul><li>Überprüfen Sie, ob Ihre Server- und Clientzertifizierung über die erforderliche EKU-OID verfügt. Wenn dies nicht der Fall ist, aktualisieren Sie Ihre Zertifizierung.</li><li>Überprüfen Sie, ob Ihr Stammzertifikat ungültig ist. Wenn dies der Fall ist, aktualisieren Sie das Stammzertifikat.</li><li>So deaktivieren Sie die Änderung: Wenn Sie das Zertifikat nicht aktualisieren können, können Sie diese wichtige Änderung mit der folgenden Konfigurationsänderung vorübergehend umgehen. Wenn Sie die Änderung deaktivieren, wird Ihr System jedoch für das Sicherheitsproblem anfällig.</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.7.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
