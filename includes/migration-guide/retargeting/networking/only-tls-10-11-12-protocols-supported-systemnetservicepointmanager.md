---
ms.openlocfilehash: 8438341d6fcc5cf0415a2cae059bc76477a5c5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234472"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>Nur die Protokolle TLS 1.0, 1.1 und 1.2 werden in System.Net.ServicePointManager und System.Net.Security.SslStream unterstützt

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager> und <xref:System.Net.Security.SslStream> nur eines der folgenden drei Protokolle verwenden: TLS 1.0, TLS 1.1 oder TLS 1.2. Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.|
|Vorschlag|Die empfohlene Risikominderung besteht darin, für die serverseitige App ein Upgrade auf TLS 1.0, TLS 1.1 oder TLS 1.2 vorzunehmen. Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext?displayProperty=name> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen: <ol><li>durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für <xref:System.AppContext?displayProperty=name>, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird</li><li>durch Hinzufügen der folgenden Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSchUseStrongCrypto=true&quot;/&gt;</code></li></ol>|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType></li></ul>|
