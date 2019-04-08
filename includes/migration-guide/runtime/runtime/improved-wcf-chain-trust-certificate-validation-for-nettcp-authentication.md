---
ms.openlocfilehash: e12ba8eb53e6725ebc2e1d87edff3a6a3ce2116b
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58467478"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a>Verbesserte WCF-Zertifikatkettenüberprüfung für die Net.Tcp-Zertifikatauthentifizierung

|   |   |
|---|---|
|Details|.NET Framework 4.7.2 verbessert die Zertifikatkettenüberprüfung, wenn Zertifikatauthentifizierung mit Transportsicherheit mit WCF verwendet wird. Durch diese Verbesserung müssen Clientzertifikate, die verwendet werden, um die Authentifizierung mit einem Server auszuführen, für Clientauthentifizierung konfiguriert werden.  Entsprechend müssen auch Serverzertifikate, die zur Authentifizierung eines Servers dienen, für Serverauthentifizierung konfiguriert werden. Wenn das Stammzertifikat deaktiviert ist, schlägt die Überprüfung der Zertifikatkette aufgrund dieser Änderung fehl. Für .NET Framework 3.5 und höhere Versionen wurde über das Windows-Sicherheitsrollup die gleiche Änderung vorgenommen. Weitere Informationen finden Sie [hier](https://support.microsoft.com/en-us/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Diese Änderung ist standardmäßig aktiviert und kann durch eine Konfigurationseinstellung deaktiviert werden.|
|Vorschlag|<ul><li>Überprüfen Sie, ob Ihre Server- und Clientzertifizierung über die erforderliche EKU-OID verfügt. Wenn dies nicht der Fall ist, aktualisieren Sie Ihre Zertifizierung.</li><li>Überprüfen Sie, ob Ihr Stammzertifikat ungültig ist. Wenn dies der Fall ist, aktualisieren Sie das Stammzertifikat.</li><li>So deaktivieren Sie die Änderung: Wenn Sie das Zertifikat nicht aktualisieren können, können Sie diesen Breaking Change mit der folgenden Konfigurationseinstellung vorübergehend umgehen. Wenn Sie den Breaking Change deaktivieren, wird Ihr System jedoch für das Sicherheitsproblem anfällig.</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Laufzeit|

