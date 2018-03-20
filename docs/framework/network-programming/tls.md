---
title: "Transport Layer Security (TLS) bewährte Methoden für .NET Framework"
description: "Beschreibt bewährte Methoden, die mithilfe von Transport Layer Security (TLS) mit .NET Framework"
ms.date: 03/15/2018
ms.prod: .net-framework
ms.topic: article
helpviewer_keywords:
- sending data, Internet security
- protocols, Internet security
- Network security
- network resources, Internet security
- receiving data, Internet security
- authentication [.NET Framework], Internet security
- Internet, security
- security [.NET Framework], Internet
- permissions [.NET Framework], Internet
author: blowdart
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64829eee5b21a44acb18cbec9b901d77d49cab90
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2018
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Transport Layer Security (TLS) bewährte Methoden für .NET Framework

Das Transport Layer Security (TLS)-Protokoll ist ein dem Branchenstandard soll dabei helfen, den Schutz von Informationen über das Internet kommuniziert. [TLS 1.2](https://tools.ietf.org/html/rfc5246) ist die neueste veröffentlichte Standard und bietet sicherheitsverbesserungen gegenüber vorherigen Versionen. TLS 1.2 schließlich ersetzt werden durch [TLS 1.3](https://tools.ietf.org/html/draft-ietf-tls-tls13-22). Dieser Artikel stellt Empfehlungen zum Sichern von .NET Framework-Anwendungen, die TLS-Protokoll verwenden.

Um sicherzustellen, dass .NET Framework-Anwendungen sicher bleiben, sollten die TLS-Protokollversion **nicht** hartcodiert werden. .NET Framework-Anwendungen sollten die TLS-Version verwenden, die das Betriebssystem (BS) unterstützt.

Dieses Dokument wendet sich an Entwickler, sind:

- Direkt mit der <xref:System.Net> APIs (z. B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Direkt mit WCF-Clients und Dienste mithilfe der <xref:System.ServiceModel?displayProperty=nameWithType> Namespace.
- Mit [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) Web- und Workerrollen Rollen zu hosten und Ausführen der Anwendung. Finden Sie unter der [Azure Cloud Services](#azure-cloud-services) Abschnitt.

Es wird empfohlen, die Sie:

- .NET Framework 4.7 oder höher bei Ihren apps als Ziel. .NET Framework-Zielversion 4.7.1 oder höher für die WCF-apps.
- Geben Sie die TLS-Version nicht. Konfigurieren Sie den Code, um das Betriebssystem auf dem TLS-Protokollversion entscheiden zu können.
- Führen Sie eine Überwachung gründliche Code, um sicherzustellen, dass Sie eine TLS / SSL-Version nicht angegeben haben.

Wenn Ihre app das Betriebssystem die TLS-Version auswählen kann:

- Er nutzt automatisch neue Protokolle in Zukunft, z. B. TLS 1.3 hinzugefügt.
- Das Betriebssystem blockiert Protokolle, die nicht für Sicherheit ermittelt werden.

Der Abschnitt [überwachen Sie den Code, und codeänderungen vornehmen](#audit-your-code-and-make-code-changes) Überwachung und Aktualisierung des Codes behandelt.

In diesem Artikel wird erläutert, wie ermöglichen, die Ihre app ausgerichtet ist und ausgeführt wird, auf die höchste Sicherheit für die Version von .NET Framework verfügbar wird. Wenn eine app explizit einen Security-Protokoll und Version festlegt, "OPTS" Out andere Alternative, und "OPTS" außerhalb des .NET Framework und OS-Standardverhalten. Wenn Sie Ihre app, damit eine TLS 1.2-Verbindung ausgehandelt werden soll, wird verhindert, dass explizit festlegen, auf eine niedrigere Version von TLS eine TLS 1.2-Verbindung.

Wenn Sie hartcodierten eine Protokollversion nicht vermeiden lassen, wird dringend empfohlen, dass Sie TLS 1.2 angeben. Anleitungen zum Identifizieren und Entfernen von TLS 1.0 Abhängigkeiten Herunterladen der [zur Lösung des Problems der TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266) Whitepaper.

WCF unterstützt TLS 1.0, 1.1 und 1.2 im .NET Framework 4.7 als Standard. Beginnen mit .NET Framework 4.7.1, konfiguriert die WCF-Standardwerte für das Betriebssystem Version. Wenn eine Anwendung mit explizit konfiguriert ist `SslProtocols.None`, WCF verwendet die Betriebssystem-Standardeinstellung, wenn der NetTcp-Transport verwendet.

Stellen Sie Fragen zu diesem Dokument in der GitHub-Problem [Transport Layer Security (TLS) bewährte Methoden mit .NET Framework](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>Überwachen Sie den Code, und nehmen codeänderungen vor

Überprüfen Sie für ASP.NET-Anwendungen den `<system.web><httpRuntime targetFramework>` Element des _"Web.config"_ , überprüfen Sie die vorgesehene Version von .NET Framework verwenden.

Windows Forms und andere Anwendungen finden Sie unter [wie: eine Version von .NET Framework als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

Verwenden Sie in den folgenden Abschnitten, um sicherzustellen, dass Sie nicht über eine bestimmte TLS / SSL-Version verwenden.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Wenn die app auf .NET Framework 4.7 oder höher abzielt

Die folgenden Abschnitte zeigen die überprüfen, ob Sie eine bestimmte TLS / SSL-Version nicht verwenden.

### <a name="for-http-networking"></a>Für HTTP-Netzwerke

<xref:System.Net.ServicePointManager>, mit .NET Framework 4.7 und höheren Versionen wird standardmäßig auf das Betriebssystem auswählen der besten Security-Protokoll und Version. Um die beste Wahl des Standard-BS abzurufen, wenn möglich, nicht legen Sie einen Wert für die <xref:System.Net.ServicePointManager.SecurityProtocol> Eigenschaft. Legen Sie sie andernfalls auf <xref:System.Net.SecurityProtocolType.SystemDefault> fest.

Der Rest dieses Artikels ist nicht relevant, beim Abzielen auf .NET Framework 4.7 oder höher für HTTP-Netzwerke.

### <a name="for-tcp-sockets-networking"></a>Für TCP-Sockets networking

<xref:System.Net.Security.SslStream>, mit .NET Framework 4.7 und höheren Versionen wird standardmäßig auf das Betriebssystem auswählen der besten Security-Protokoll und Version. Um die beste Wahl des Standard-BS abzurufen, wenn möglich, verwenden Sie keine methodenüberladungen <xref:System.Net.Security.SslStream> , die eine explizite dauern <xref:System.Security.Authentication.SslProtocols> Parameter. Andernfalls übergeben <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Es wird empfohlen, dass Sie nicht verwenden <xref:System.Security.Authentication.SslProtocols.Default>; Einstellung `SslProtocols.Default` erzwingt die Verwendung von SSL 3.0 /TLS 1.0 und zu verhindern, dass TLS 1.2.

Setzen Sie keinen Wert für die <xref:System.Net.ServicePointManager.SecurityProtocol> -Eigenschaft (für HTTP-Netzwerke).

Verwenden Sie keine überladenen Methode <xref:System.Net.Security.SslStream> , die eine explizite dauern <xref:System.Security.Authentication.SslProtocols> Parameter (für TCP-Sockets Netzwerke). Wenn Sie Ihre app auf .NET Framework 4.7 oder höher neu zuweisen, müssen Sie die best Practices-Empfehlung befolgen, werden.

Im weiteren Verlauf dieses Themas ist nicht relevant, wenn als Ziel .NET Framework 4.7 oder höher für TCP-Netzwerken Sockets.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Für WCF TCP transport mithilfe der transportsicherheit mit Zertifikatanmeldeinformationen

WCF verwendet denselben Netzwerkstapel, wie der Rest des .NET Framework.

Wenn Sie 4.7.1 abzielen, wird WCF konfiguriert das Betriebssystem, das beste Sicherheitsprotokoll standardmäßig auszuwählen, wenn nicht ausdrücklich konfiguriert:

- In der Anwendungskonfigurationsdatei.
- **Oder**, in der Anwendung im Quellcode.

Standardmäßig können Sie .NET Framework 4.7 und höheren Versionen für die Verwendung von TLS 1.2 konfiguriert und lässt Verbindungen mithilfe von TLS 1.1 oder TLS 1.0. Konfigurieren von WCF, damit das Betriebssystem das Sicherheitsprotokoll für das beste auswählen, indem Sie die zu verwendende Bindung konfigurieren können <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Dies kann festgelegt werden, auf <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` aus zugegriffen werden kann <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` aus zugegriffen werden kann <xref:System.ServiceModel.NetTcpBinding.Security>.

Wenn Sie eine benutzerdefinierte Bindung verwenden:

- Konfigurieren von WCF, um das Betriebssystem auf das Sicherheitsprotokoll für das beste durch Festlegen von ermöglichen <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> verwenden <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **Oder** konfigurieren Sie das Protokoll mit dem Konfigurationspfad verwendet `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Wenn Sie sind **nicht** mit einer benutzerdefinierten Bindung **und** Sie Ihre WCF-Bindung, die mithilfe der Konfiguration festlegen, legen Sie das Protokoll mit dem Konfigurationspfad verwendet `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Für die WCF-Nachrichtensicherheit mit Zertifikatanmeldeinformationen

.NET Framework 4.7 und höheren Versionen wird standardmäßig verwendet das Protokoll angegeben, der <xref:System.Net.ServicePointManager.SecurityProtocol> Eigenschaft. Wenn die [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` festgelegt ist, um `true`, WCF, wählt das beste-Protokoll, bis zu TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Wenn die app vor 4.7 eine Version von .NET Framework abzielt

Überwachen Sie den Code, um sicherzustellen, dass Sie eine bestimmte TLS / SSL-Version mit den folgenden Abschnitten nicht festlegen:

### <a name="for-net-framework-46---462-and-not-wfc"></a>Für .NET Framework 4.6 - 4.6.2 und nicht einem WFC

Legen Sie die `DontEnableSystemDefaultTlsVersions` `AppContext` wechseln Sie zur `false`. Finden Sie unter [Konfigurieren der Sicherheit über AppContext Switches](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Für WCF mit .NET Framework 4.6 - 4.6.2 Zertifikats-Anmeldeinformationen mit TCP-Transport-Sicherheit

Sie müssen die neuesten OS-Patches installieren. Finden Sie unter [Sicherheitsupdates](#security-updates).

Der WCF-Frameworks wählt automatisch das höchste verfügbar, bis zu TLS 1.2-Protokoll, es sei denn, Sie explizit eine Protokollversion konfigurieren. Weitere Informationen finden Sie im vorherigen Abschnitt [für WCF-TCP-Transport mithilfe der transportsicherheit mit Zertifikatanmeldeinformationen](#wcf-tcp-cert).

### <a name="for-net-framework-35---451-and-not-wcf"></a>Für .NET Framework 3.5 - 4.5.1 und nicht von WCF

Es wird empfohlen, dass Sie Ihre app auf .NET Framework 4.7 oder höher aktualisieren. Wenn Sie nicht aktualisieren können, gehen Sie folgendermaßen vor. Irgendwann in der Zukunft Ihre Anwendung möglicherweise erst ein upgrade auf .NET Framework 4.7 oder höhere Versionen.

Legen Sie die [SchUseStrongCrypto](#schusestrongcrypto) und [SystemDefaultTlsVersions](#systemdefaulttlsversions) Registrierungsschlüssel auf 1. Finden Sie unter [Konfigurieren der Sicherheit über die Windows-Registrierung](#configuring-security-via-the-windows-registry). .NET Framework, Version 3.5 unterstützt die `SchUseStrongCrypto` flag nur, wenn ein expliziter TLS-Wert übergeben wird.

Wenn Sie .NET Framework 3.5 ausgeführt werden, müssen Sie ein im laufenden Systembetrieb Upgradepatch nicht installieren, damit das Programm TLS 1.2 angegeben werden können:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Zuverlässigkeit Rollup HR-1605 - Unterstützung für TLS System Standard Versionen in .NET Framework 3.5.1 unter Windows 7 SP1 und Server 2008 R2 SP1 enthalten |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Zuverlässigkeit Rollup HR-1605 - Unterstützung für TLS System Standard-Versionen in .NET Framework 3.5 unter Windows Server 2012 enthalten |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Zuverlässigkeit Rollup HR-1605 - Unterstützung für TLS System Standard-Versionen enthalten, in der .NET Framework 3.5 auf Windows 8.1 und Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | 1605 Hotfixrollup 3154521 für .NET Framework 4.5.2 und 4.5.1 unter Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Für WCF mit .NET Framework 3.5 - 4.5.2 Zertifikats-Anmeldeinformationen mit TCP-Transport-Sicherheit

Diese Versionen von WCF-Framework werden hartcodierte Werte SSL 3.0 und TLS 1.0 verwenden. Diese Werte können nicht geändert werden. Sie müssen aktualisieren und .NET Framework 4.6 oder höher, um TLS 1.1 und 1.2 verwenden, neu zuweisen.

## <a name="if-your-app-targets-net-framework-35"></a>Wenn die app auf .NET Framework 3.5 abzielt.

Wenn Sie explizit einem Sicherheitsprotokolls anstatt von .NET Framework oder der OS Kommissionierung das Sicherheitsprotokoll festlegen müssen, fügen `SecurityProtocolTypeExtensions` und `SslProtocolsExtension` Enumerationen in den Code. `SecurityProtocolTypeExtensions` und `SslProtocolsExtension` enthalten Werte für `Tls12`, `Tls11`, und die `SystemDefault` Wert. Finden Sie unter [Unterstützung für TLS System Standard-Versionen in .NET Framework 3.5 unter Windows 8.1 und Windows Server 2012 R2 enthalten](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Konfigurieren der Sicherheit über AppContext Kontextwechsel (für .NET Framework 4.6 oder höher)

Die [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Switches, die in diesem Abschnitt beschriebenen sind relevant Wenn Ihre app aufgerichtet ist, oder auf .NET Framework 4.6 oder höher ausgeführt wird. Ob standardmäßig, oder indem Sie sie explizit festlegen, die Schalter liegen `false` Wenn möglich. Wenn Sie die Sicherheit über eine oder beide Optionen konfigurieren möchten, klicken Sie dann geben Sie keinen Security-Protokollwert in Ihrem Code; Dies überschreibt also die Switches.

Die Switches verwenden denselben Effekt, ob Sie HTTP-Netzwerk bietet (<xref:System.Net.ServicePointManager>) oder TCP-Socket-Netzwerke (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Der Wert `false` für `Switch.System.Net.DontEnableSchUseStrongCrypto` bewirkt, dass die app auf starke Kryptografie. Der Wert `false` für `DontEnableSchUseStrongCrypto` sicherer Netzwerkprotokolle (TLS 1.2, TLS 1.1 und TLS 1.0) verwendet und Protokolle, die nicht sicher sind blockiert. Weitere Informationen finden Sie unter [der SCH_USE_STRONG_CRYPTO Flag](#the-schusestrongcrypto-flag). Der Wert `true` deaktiviert die starken Kryptografie für Ihre app.

Wenn die app auf .NET Framework 4.6 oder höher abzielt, wird dieser Schalter standardmäßig `false`. Das ist eine sichere Standardeinstellung, es wird empfohlen. Wenn Ihre app auf .NET Framework 4.6 ausgeführt wird, jedoch auf eine frühere Version abzielt, wird der Schalter standardmäßig `true`. In diesem Fall sollten Sie explizit es festlegen `false`.

`DontEnableSchUseStrongCrypto` müssen Sie nur einen Wert von `true` legacy-Diensten herstellen, für die starken Kryptografie nicht unterstützt und kann nicht aktualisiert werden sollen.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Der Wert `false` für `Switch.System.Net.DontEnableSystemDefaultTlsVersions` bewirkt, dass Ihre app, um das Betriebssystem auswählen des Protokolls zu ermöglichen. Ein Wert von `true` bewirkt, dass die app auf Protokolle, die von .NET Framework abgerufen.

Wenn die app auf .NET Framework 4.7 oder höher abzielt, wird dieser Schalter standardmäßig `false`. Das ist eine sichere Standardwert, den wir empfehlen. Wenn Ihre app auf .NET Framework 4.7 oder höher ausgeführt wird, jedoch auf eine frühere Version abzielt, wird der Schalter standardmäßig `true`. In diesem Fall sollten Sie explizit es festlegen `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Der Wert `false` für `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` bewirkt, dass die Anwendung verwendet den Wert im definierten `ServicePointManager.SecurityProtocols` für die nachrichtensicherheit Zertifikats-Anmeldeinformationen verwenden. Der Wert `true` verwendet das höchste verfügbar, bis zu TLS1. 0-Protokoll

Für Anwendungen für .NET Framework 4.7 und höheren Versionen dieser Wert liegt standardmäßig `false`. Für Anwendungen, die auf .NET Framework 4.6.2 und früher: Dieser Wert liegt standardmäßig `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Der Wert `false` für `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` legt die Standardkonfiguration, um das Betriebssystem auswählen des Protokolls zu ermöglichen. Ein Wert von `true` auf das höchste verfügbar, bis zu TLS 1.2-Protokoll wird der Standardwert festgelegt.

Für Anwendungen für .NET Framework 4.7.1 und höheren Versionen dieser Wert liegt standardmäßig `false`. Für Anwendungen, die auf .NET Framework 4.7 und früher, dieser Wert liegt standardmäßig `true`.

Weitere Informationen zu TLS-Protokolle, finden Sie unter [Entschärfung: TLS-Protokolle](../migration-guide/mitigation-tls-protocols.md). Weitere Informationen zu `AppContext` Switches finden Sie unter [ `<AppContextSwitchOverrides> Element` ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Konfigurieren der Sicherheit über die Windows-Registrierung

Wenn eine oder beide festlegen `AppContext` bei Schaltern wird nicht machbar, können Sie die Sicherheitsprotokolle, die Ihre app, mit der Windows-Registrierungsschlüssel, der in diesem Abschnitt beschrieben verwendet steuern. Sie können nicht in der Lage sind, verwenden Sie eine oder beide der `AppContext` umgeschaltet, wenn die app auf .NET Framework-Version vor 4.6 abzielt, oder Sie können die Konfigurationsdatei können nicht bearbeitet. Wenn Sie die Sicherheit mit der Registrierung konfigurieren möchten, klicken Sie dann geben Sie keinen Security-Protokollwert in Ihrem Code; Dies überschreibt also die Registrierung.

Die Namen der Registrierungsschlüssel ähneln den Namen des entsprechenden `AppContext` schaltet aber ohne eine `DontEnable` , der den Namen vorangestellt wird. Z. B. die `AppContext` wechseln `DontEnableSchUseStrongCrypto` heißt der Registrierungsschlüssel [SchUseStrongCrypto](#schusestrongcrypto).

Diese Schlüssel stehen in allen .NET Framework-Versionen, die für die aktuellen Sicherheitspatches vorhanden ist. Finden Sie unter [Sicherheitsupdates](#security-updates).

Alle der unten beschriebenen Registrierungsschlüssel haben die gleiche Wirkung, ob Sie HTTP-Netzwerk bietet (<xref:System.Net.ServicePointManager>) oder TCP-Socket-Netzwerke (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

Die `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` Registrierungsschlüssel ist einen Wert vom Typ DWORD. Der Wert 1 bewirkt, dass die app auf starke Kryptografie. Die starke Kryptografie sicherer Netzwerkprotokolle (TLS 1.2, TLS 1.1 und TLS 1.0) verwendet und Protokolle, die nicht sicher sind blockiert. Der Wert 0 deaktiviert die starken Kryptografie. Weitere Informationen finden Sie unter [der SCH_USE_STRONG_CRYPTO Flag](#the-schusestrongcrypto-flag).

Wenn die app auf .NET Framework 4.6 oder höher abzielt, wird standardmäßig dieser Schlüssel auf den Wert 1. Das ist eine sichere Standardwert, den wir empfehlen. Wenn Ihre app auf .NET Framework 4.6 ausgeführt wird, weist aber eine frühere Version, und klicken Sie dann auf den Schlüssel hat den Standardwert 0. In diesem Fall sollten Sie explizit den Wert auf 1 festlegen.

Dieser Schlüssel sollte nur einen Wert von 0 aufweisen, wenn Sie älteren Diensten herstellen, für die starken Kryptografie nicht unterstützt und kann nicht aktualisiert werden müssen.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

Die `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` Registrierungsschlüssel ist einen Wert vom Typ DWORD. Der Wert 1 bewirkt, dass Ihre app, um das Betriebssystem auswählen des Protokolls zu ermöglichen. Der Wert 0 bewirkt, dass die app auf Protokolle, die von .NET Framework abgerufen.

`<VERSION>` v4.0.30319 (für .NET Framework 4 und höher) oder v2.0.50727 muss (für .NET Framework 3.5) sein.

Wenn die app auf .NET Framework 4.7 oder höher abzielt, wird standardmäßig dieser Schlüssel auf den Wert 1. Das ist eine sichere Standardwert, den wir empfehlen. Wenn Ihre app auf .NET Framework 4.7 oder höher ausgeführt wird, jedoch auf eine frühere Version abzielt, wird standardmäßig der Schlüssel auf 0 ein. In diesem Fall sollten Sie explizit den Wert auf 1 festlegen.

Weitere Informationen finden Sie unter [kumulative Update für Windows 10 Version 1511 und Windows Server 2016 Technical Preview 4: 10. Mai 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Weitere Informationen mit .NET Framework 3.5.1 finden Sie unter [Unterstützung für TLS System Standard-Versionen in .NET Framework 3.5.1 unter Windows 7 SP1 und Server 2008 R2 SP1 enthaltenen](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

Die folgenden _. REG_ Datei legt die Registrierungsschlüssel und deren Varianten auf ihre am sicheren Werte fest:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001
```

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Konfigurieren von Schannel-Protokolle in der Windows-Registrierung

Sie können die Registrierung für eine präzisere Kontrolle über die Protokolle, die Ihre app Client und/oder Server ausgehandelt. Netzwerk für Ihre app durchläuft Schannel (also in einen anderen Namen für [Secure Channel](https://msdn.microsoft.com/library/windows/desktop/aa380123). Durch Konfigurieren von `Schannel`, Sie können das Verhalten Ihrer app konfigurieren.

Beginnen Sie mit der `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols` Registrierungsschlüssel. Sie können alle Unterschlüssel unter diesem Schlüssel erstellen, in der Menge `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1`, und `TLS 1.2`. Sie können unter jeder dieser Unterschlüssel Unterschlüssel erstellen `Client` und/oder `Server`. Klicken Sie unter `Client` und `Server`, können Sie den DWORD-Werte erstellen `DisabledByDefault` (0 oder 1) und `Enabled` ("0" oder "0xFFFFFFFF").

## <a name="the-schusestrongcrypto-flag"></a>Das Flag SCH_USE_STRONG_CRYPTO

Wenn es aktiviert ist (standardmäßig durch eine `AppContext` zu wechseln, oder von der Windows-Registrierung), .NET Framework verwendet die `SCH_USE_STRONG_CRYPTO` kennzeichnen, wenn Ihre app eine TLS-Sicherheitsprotokoll anfordert. Die `SCH_USE_STRONG_CRYPTO` Flag kann in der Standardeinstellung aktiviert werden, mit der `AppContext` zu wechseln, oder mit der Registrierung. Das Betriebssystem übergibt das Flag `Schannel`um, um bekannte schwache Kryptografiealgorithmen deaktivieren anzuweisen, dieses Feld enthält die Testsammlungen und TLS/SSL-Protokollversionen, die andernfalls für eine bessere Interoperabilität aktiviert werden können. Weitere Informationen finden Sie unter:

- [Secure Channel](https://msdn.microsoft.com/library/windows/desktop/aa380123)
- [SCHANNEL_CRED-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa379810)

Die `SCH_USE_STRONG_CRYPTO` Flag wird ebenfalls übergeben, um `Schannel` explizit Verwendung der `Tls` (TLS 1.0), `Tls11`, oder `Tls12` enumierationswerte von <xref:System.Net.SecurityProtocolType> oder <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Sicherheitsupdates

Die bewährten Methoden in diesem Artikel richten sich nach der neuesten Sicherheitsupdates installiert wird. Diese Updates enthalten die Möglichkeit, erweiterte .NET Framework 4.7 und höher verwenden. Aktuelle Sicherheitsupdates sind wichtig, wenn Ihre app auf .NET Framework 4.7 und höher ausgeführt wird (auch wenn es sich um eine frühere Version abzielt).

Um die .NET Framework ermöglichen die beste Version von TLS zu verwenden, wählen das Betriebssystem zu aktualisieren, müssen Sie mindestens installieren:

- Die [.NET Framework August 2017 Preview Qualität Rollup](https://blogs.msdn.microsoft.com/dotnet/2017/08/16/net-framework-august-2017-preview-of-quality-rollup).
- **Oder** der [September 2017 Sicherheit von .NET Framework und Qualität Rollup](https://blogs.msdn.microsoft.com/dotnet/2017/09/12/net-framework-september-2017-security-and-quality-rollup).

Siehe auch:

- [.NET Framework-Versionen und-Abhängigkeiten](../migration-guide/versions-and-dependencies.md)
- [Vorgehensweise: bestimmen, welche .NET Framework-Versionen installiert sind](../migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="support-for-tls-12"></a>Unterstützung für TLS 1.2

Für Ihre app zum Aushandeln von TLS 1.2, das Betriebssystem und .NET Framework-Version müssen beide TLS 1.2 zu unterstützen.

**Anforderungen an das Betriebssystem zur Unterstützung von TLS 1.2**

Zum Aktivieren oder erneutes Aktivieren von TLS 1.2 und/oder TLS 1.1 auf ein System, das sie unterstützt, finden Sie unter [registrierungseinstellungen für den Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings).

| **OS** | **TLS 1.2-Unterstützung** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | Unterstützt, und standardmäßig aktiviert. |
| Windows 8.1</br>Windows Server 2012 R2 | Unterstützt, und standardmäßig aktiviert. |
| Windows 8.0</br>Windows Server 2012 | Unterstützt, und standardmäßig aktiviert. |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | Unterstützt, jedoch nicht standardmäßig aktiviert. Finden Sie unter der [registrierungseinstellungen für den Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings) Webseite Weitere Informationen zum Aktivieren von TLS 1.2. |
| Windows Server 2008 | Unterstützung für TLS 1.2 und TLS 1.1 ist ein Update erforderlich. Finden Sie unter [Update zum Hinzufügen der Unterstützung für TLS 1.1 und TLS 1.2 in Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | Wird nicht unterstützt. |

Informationen über die TLS/SSL-Protokolle für die einzelnen Versionen von Windows standardmäßig aktiviert sind, finden Sie unter [Protokolle TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159).

**Anforderungen zur Unterstützung von TLS 1.2 mit .NET Framework 3.5**

Diese Tabelle zeigt dem Update des Betriebssystems, die Sie benötigen, um TLS 1.2 mit .NET Framework 3.5 zu unterstützen. Es wird empfohlen, dass Sie alle Betriebssystem-Updates anwenden.

| **OS** | **Minimale Update erforderlich, um TLS 1.2 mit .NET Framework 3.5 zu unterstützen.** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | [Kumulatives Update für Windows 10 Version 1511 und Windows Server 2016 Technical Preview 4: 10. Mai 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1</br>Windows Server 2012 R2 | [Unterstützung für TLS System Standard-Versionen enthalten, die in .NET Framework 3.5 auf Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0</br>Windows Server 2012 | [Unterstützung für TLS System Standard-Versionen in .NET Framework 3.5 unter Windows Server 2012 enthalten](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | [Unterstützung für TLS System Standard-Versionen enthalten, die in .NET Framework 3.5.1 unter Windows 7 SP1 und Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Unterstützung für TLS System Standard-Versionen enthalten, die in .NET Framework 2.0 SP2 unter Windows Vista SP2 und Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Nicht unterstützt |

## <a name="azure-cloud-services"></a>Azure Cloud Services

Bei Verwendung von [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) Web- und Workerrollen Rollen zu hosten und Ausführen Ihrer Anwendung sind einige Aspekte, die zur Unterstützung von TLS 1.2 berücksichtigen müssen.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>.NET Framework 4.7 ist auf Azure-Gastbetriebssystem nicht standardmäßig installiert werden.

Die neueste Version der neuen Azure Guest OS Family 5-Version (Windows Server 2016) installiert ist, 4.6.2. Welche Versionen von .NET Framework auf jedem Azure-Gastbetriebssystem installiert sind, finden Sie unter der [Azure-gastbetriebssystemversionen und SDK-Kompatibilitätsmatrix](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Wenn die app auf eine Version von .NET Framework, die nicht in der Azure-Gast-BS-Version verfügbar ist abzielt, müssen Sie ihn selbst zu installieren. Finden Sie unter [installieren Sie .NET auf Azure-Cloud-Dienstrollen](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Wenn die Framework-Installation ein Neustart erforderlich ist, können der Dienst-Rollen auch neu starten, vor dem Wechsel in den Status "bereit".

### <a name="azure-guest-os-registry-settings"></a>Registrierungseinstellungen für den Azure-Gastbetriebssystem

Das Azure-Gast-BS-image für [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) verfügt bereits über die `SchUseStrongCrypto` Registrierungsschlüssel auf den Wert 1 festgelegt. Weitere Informationen finden Sie unter [SchUseStrongCrypto](#schusestrongcrypto).

Legen Sie die [SystemDefaultTlsVersions](#systemdefaulttlsversions) Registrierungsschlüssel auf 1. Finden Sie unter [Konfigurieren der Sicherheit über die Windows-Registrierung](#configuring-security-via-the-windows-registry).
