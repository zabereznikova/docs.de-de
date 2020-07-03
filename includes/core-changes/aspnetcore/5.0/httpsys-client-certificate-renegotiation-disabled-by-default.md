---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325234"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: Neuverhandlung von Clientzertifikaten standardmäßig deaktiviert

Die Option zum Neuverhandeln einer Verbindung und Anfordern eines Clientzertifikats wurde standardmäßig deaktiviert. Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).

#### <a name="version-introduced"></a>Eingeführt in Version

ASP.NET Core 5.0

#### <a name="old-behavior"></a>Altes Verhalten

Die Verbindung kann neu verhandelt werden, um ein Clientzertifikat anzufordern.

#### <a name="new-behavior"></a>Neues Verhalten

Clientzertifikate können nur während des ersten Verbindungshandshakes angefordert werden. Weitere Informationen finden Sie im Pull Request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Neuverhandlung hat eine Reihe von Leistungs- und Deadlockproblemen verursacht. Sie wird auch in HTTP/2 nicht unterstützt. Weitere Kontextinformationen vom Zeitpunkt der Einführung der Option zur Steuerung dieses Verhaltens in ASP.NET Core 3.1 finden Sie im Issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).

#### <a name="recommended-action"></a>Empfohlene Aktion

Apps, für die Clientzertifikate erforderlich sind, sollten *netsh.exe* verwenden, um die Option `clientcertnegotiation` auf `enabled` festzulegen. Weitere Informationen finden Sie unter [netsh http-Befehle](/windows-server/networking/technologies/netsh/netsh-http).

Wenn Sie möchten, dass Clientzertifikate nur für Teile der App aktiviert sind, lesen Sie den Leitfaden unter [Optionale Clientzertifikate](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).

Wenn Sie das alte Neuverhandlungsverhalten benötigen, legen Sie `HttpSysOptions.ClientCertificateMethod` auf den alten Wert `ClientCertificateMethod.AllowRenegotiate` fest. Dies wird aus den oben und im verlinkten Leitfaden genannten Gründen nicht empfohlen.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
