---
title: Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework
description: Beschreibt bewährte Methoden für die Verwendung von Transport Layer Security (TLS) mit .NET Framework.
ms.date: 10/22/2018
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
ms.openlocfilehash: e2f8f1304de587e1bedd8cde60e665971d903183
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937693"
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework

Das TLS-Protokoll (Transport Layer Security) ist ein Industriestandard zum Schutz von Daten, die über das Internet übertragen werden. [TLS 1.2](https://tools.ietf.org/html/rfc5246) ist ein Standard, der Sicherheitsverbesserungen gegenüber früheren Versionen umfasst. TLS 1.2 wird schließlich durch den neuesten freigegebenen Standard [TLS 1.3](https://tools.ietf.org/html/rfc8446) ersetzt, der schneller ist und eine erhöhte Sicherheit bietet. Dieser Artikel enthält Empfehlungen zur Sicherung von .NET Framework-Anwendungen, die das TLS-Protokoll verwenden.

Um die Sicherheit von .NET Framework-Anwendungen zu gewährleisten, sollte die TLS-Version **nicht** hartcodiert sein. .NET Framework-Anwendungen sollten die vom Betriebssystem unterstützte TLS-Version verwenden.

Dieses Dokument richtet sich an Entwickler, für die Folgendes zutrifft:

- Sie verwenden direkt die <xref:System.Net>-APIs (z.B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Sie verwenden direkt WCF-Clients und -Dienste über den Namespace <xref:System.ServiceModel?displayProperty=nameWithType>.
- Sie verwenden Web- und Workerrollen von [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) zum Hosten und Ausführen Ihrer Anwendung. Siehe Abschnitt [Azure Cloud Services](#azure-cloud-services).

Folgendes wird empfohlen:

- Verwenden Sie .NET Framework 4.7 oder höhere Versionen für Ihre Apps. Verwenden Sie .NET Framework 4.7.1 oder höhere Versionen für Ihre WCF-Apps.
- Geben Sie keine TLS-Version an. Konfigurieren Sie Ihren Code so, dass das Betriebssystem über die TLS-Version entscheidet.
- Führen Sie eine gründliche Codeüberprüfung durch, um sicherzustellen, dass Sie keine TLS- oder SSL-Version festlegen.

Wenn die TLS-Version in Ihrer App vom Betriebssystem gewählt wird:

- Werden automatisch neue Protokolle genutzt, die in Zukunft hinzugefügt werden, wie z.B. TLS 1.3.
- Blockiert das Betriebssystem Protokolle, die als nicht sicher erkannt werden.

Der Abschnitt [Überprüfen Ihres Codes und vornehmen von Codeänderungen](#audit-your-code-and-make-code-changes) unterstützt Sie dabei, Ihren Code zu überprüfen und zu aktualisieren.

Dieser Artikel erklärt, wie Sie die höchste Sicherheit für die Version des .NET-Frameworks erreichen, auf die Ihre App abzielt und unter der sie ausgeführt wird. Wenn ein Sicherheitsprotokoll und eine Sicherheitsversion von einer App explizit festlegt werden, sind somit jede andere Alternative und das Standardverhalten von .NET Framework und dem Betriebssystem ausgeschlossen. Wenn Sie möchten, dass Ihre App eine TLS 1.2-Verbindung aushandeln kann, wird dies durch das explizite Festlegen auf eine niedrigere Version als TLS 1.2 verhindert.

Sollte sich die Hartcodierung einer Protokollversion nicht vermeiden lassen, wird dringend empfohlen, TLS 1.2 festzulegen. Eine Anleitung zum Identifizieren und Entfernen von TLS 1.0-Abhängigkeiten finden Sie im Whitepaper [Solving the TLS 1.0 Problem](https://www.microsoft.com/download/details.aspx?id=55266) (Lösung des TLS 1.0-Problems), das als Download verfügbar ist.

WCF unterstützt TLS 1.0, 1.1 und 1.2 als Standard in .NET Framework 4.7. Ab .NET Framework 4.7.1 verwendet WCF standardmäßig die vom Betriebssystem konfigurierte Version. Wenn eine Anwendung explizit mit `SslProtocols.None` konfiguriert ist, verwendet WCF die Standardeinstellung des Betriebssystems für den NetTcp-Transport.

Fragen zu diesem Dokument können Sie im GitHub-Thema [Transport Layer Security (TLS) best practices with the .NET Framework](https://github.com/dotnet/docs/issues/4675) (Bewährte Methoden für TLS mit .NET Framework) stellen.

## <a name="audit-your-code-and-make-code-changes"></a>Überprüfen Ihres Codes und vornehmen von Codeänderungen

Für ASP.NET-Anwendungen überprüfen Sie das Element `<system.web><httpRuntime targetFramework>` von _web.config_, um sicherzustellen, dass Sie die beabsichtigte Version von .NET Framework verwenden.

Für Windows Forms und andere Anwendungen lesen Sie [Vorgehensweise: Erstellen von Projekten für eine bestimmte .NET Framework-Version](/visualstudio/ide/visual-studio-multi-targeting-overview).

Verwenden Sie die folgenden Abschnitte, um sicherzustellen, dass Sie keine bestimmte TLS- oder SSL-Version verwenden.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Wenn Ihre App auf .NET Framework 4.7 oder höhere Versionen abzielt

Die folgenden Abschnitte zeigen, wie Sie sicherstellen können, dass Sie keine bestimmte TLS- oder SSL-Version verwenden.

### <a name="for-http-networking"></a>Für HTTP-Netzwerke

Bei Verwendung von .NET Framework 4.7 und höheren Versionen nutzt <xref:System.Net.ServicePointManager> das Standardsicherheitsprotokoll, das im Betriebssystem konfiguriert ist. Damit die Standardauswahl des Betriebssystems übernommen wird, sofern möglich, legen Sie keinen Wert für die <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft fest. Diese ist standardmäßig auf <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType> festgelegt.

Da die Einstellung für <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType> bewirkt, dass <xref:System.Net.ServicePointManager> das vom Betriebssystem konfigurierte Standardsicherheitsprotokoll verwendet, wird Ihre Anwendung je nach Betriebssystem möglicherweise etwas anders ausgeführt. Ein Beispiel: Windows 7 SP1 verwendet TLS 1.0, während Windows 8 und Windows 10 TLS 1.2 nutzen.

Der Rest dieses Artikels ist nicht relevant, wenn .NET Framework 4.7 oder höhere Versionen für HTTP-Netzwerke verwendet werden sollen.

### <a name="for-tcp-sockets-networking"></a>Für TCP-Socketnetzwerke

<xref:System.Net.Security.SslStream> wird bei Verwendung von .NET Framework 4.7 oder höheren Versionen standardmäßig auf die Vorgabe des Betriebssystems gesetzt, welches das beste Sicherheitsprotokoll und die beste Version auswählt. Damit standardmäßig die beste Wahl des Betriebssystems übernommen wird, verwenden Sie möglichst nicht die Methodenüberladungen von <xref:System.Net.Security.SslStream>, die einen expliziten <xref:System.Security.Authentication.SslProtocols>-Parameter übernehmen. Andernfalls übergeben Sie <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Die Verwendung von <xref:System.Security.Authentication.SslProtocols.Default> wird nicht empfohlen. Durch die Einstellung `SslProtocols.Default` wird die Verwendung von SSL 3.0/TLS 1.0 erzwungen und TLS 1.2 nicht genutzt.

Legen Sie (bei HTTP-Netzwerken) keinen Wert für die <xref:System.Net.ServicePointManager.SecurityProtocol>-Eigenschaft fest.

Verwenden Sie (bei TCP-Socketnetzwerken) keine Methodenüberladungen von <xref:System.Net.Security.SslStream>, die einen expliziten <xref:System.Security.Authentication.SslProtocols>-Parameter übernehmen. Wenn Sie Ihre App erneut auf .NET Framework 4.7 oder höhere Versionen ausrichten, folgen Sie der Empfehlung in den bewährten Methoden.

Der Rest dieses Themas ist nicht relevant, wenn es um .NET Framework 4.7 oder höhere Versionen für TCP-Socketnetzwerke geht.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Für WCF-TCP-Transport unter Berücksichtigung der Transportsicherheit mit Zertifikatanmeldeinformationen

WCF verwendet den gleichen Netzwerkstack wie der Rest des .NET Frameworks.

Wenn Sie auf 4.7.1 abzielen, ist WCF so konfiguriert, dass das Betriebssystem standardmäßig das beste Sicherheitsprotokoll auswählen kann, sofern es nicht explizit an einem der folgenden Orte festgelegt ist:

- In der Konfigurationsdatei Ihrer Anwendung
- **Oder**, im Quellcode Ihrer Anwendung

.NET Framework 4.7 und höhere Versionen sind standardmäßig für die Verwendung von TLS 1.2 konfiguriert und erlauben Verbindungen mit TLS 1.1 oder TLS 1.0. Konfigurieren Sie WCF, damit das Betriebssystem das beste Sicherheitsprotokoll auswählen kann, indem Sie für Ihre Bindung die Verwendung von <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType> festlegen. Dies kann auf <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols> festgelegt werden. `SslProtocols.None` kann von <xref:System.ServiceModel.NetTcpSecurity.Transport> aus aufgerufen werden. `NetTcpSecurity.Transport` kann von <xref:System.ServiceModel.NetTcpBinding.Security> aus aufgerufen werden.

Bei Verwendung einer benutzerdefinierten Bindung:

- Konfigurieren Sie WCF, damit das Betriebssystem das beste Sicherheitsprotokoll auswählen kann, indem Sie für <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType> die Verwendung von <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> festlegen.
- **Oder** konfigurieren Sie das Protokoll, das mit dem Konfigurationspfad `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols` verwendet wird.

Wenn Sie **keine** benutzerdefinierte Bindung verwenden **und** Ihre WCF-Bindung über die Konfiguration einstellen, legen Sie das verwendete Protokoll mit dem Konfigurationspfad `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols` fest.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Für WCF-Nachrichtensicherheit mit Zertifikatanmeldeinformationen

.NET Framework 4.7 und höhere Versionen verwenden standardmäßig das in der <xref:System.Net.ServicePointManager.SecurityProtocol>-Eigenschaft angegebene Protokoll. Wenn die [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` auf `true` gesetzt ist, wählt WCF das beste Protokoll bis TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Wenn Ihre App auf eine höhere .NET Framework-Version als 4.7 abzielt

Überprüfen Sie Ihren Code, um sicherzustellen, dass Sie keine bestimmte TLS- oder SSL-Version verwenden, wie in den folgenden Abschnitten beschrieben:

### <a name="for-net-framework-46---462-and-not-wcf"></a>Für .NET Framework 4.6 bis 4.6.2 und ohne WCF

Setzen Sie die `DontEnableSystemDefaultTlsVersions` `AppContext`-Option auf `false`. Siehe [Konfigurieren der Sicherheit über AppContext-Switches](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Für WCF mit .NET Framework 4.6 bis 4.6.2 unter Berücksichtigung der Transportsicherheit mit Zertifikatanmeldeinformationen

Sie müssen die neuesten Betriebssystempatches installieren. Siehe [Sicherheitsupdates](#security-updates).

Das WCF-Framework wählt automatisch das höchste bis TLS 1.2 verfügbare Protokoll, es sei denn, Sie konfigurieren explizit eine Protokollversion. Weitere Informationen finden Sie im vorhergehenden Abschnitt [Für WCF-TCP-Transport unter Berücksichtigung der Transportsicherheit mit Zertifikatanmeldeinformationen](#wcf-tcp-cert).

### <a name="for-net-framework-35---452-and-not-wcf"></a>Für .NET Framework 3.5 bis 4.5.2 und ohne WCF

Es wird empfohlen, ein Upgrade Ihrer App auf .NET Framework 4.7 oder höher auszuführen. Wenn Sie kein Upgrade ausführen können, gehen Sie wie folgt vor. Möglicherweise tritt irgendwann in Ihrer Anwendung ein Fehler auf, bis Sie ein Upgrade auf .NET Framework 4.7 oder höher ausgeführt haben.

Setzen Sie die Registrierungsschlüssel [SchUseStrongCrypto](#schusestrongcrypto) und [SystemDefaultTlsVersions](#systemdefaulttlsversions) auf 1. Siehe [Konfigurieren der Sicherheit über die Windows-Registrierung](#configuring-security-via-the-windows-registry). Die .NET Framework-Version 3.5 unterstützt das Flag `SchUseStrongCrypto` nur, wenn ein expliziter TLS-Wert übergeben wird.

Wenn Sie .NET Framework 3.5 ausführen, müssen Sie einen Hotpatch installieren, damit TLS 1.2 von Ihrem Programm festgelegt werden kann:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Zuverlässigkeitsrollup HR-1605 – Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5.1 unter Windows 7 SP1 und Windows Server 2008 R2 SP1 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Zuverlässigkeitsrollup HR-1605 – Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5 unter Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Zuverlässigkeitsrollup HR-1605 – Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5 unter Windows 8.1 und Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | 1605 Hotfixrollup 3154521 für das .NET Framework 4.5.2 und 4.5.1 unter Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Für WCF mit .NET Framework 3.5 bis 4.5.2 unter Berücksichtigung der Transportsicherheit mit Zertifikatanmeldeinformationen

Diese Versionen des WCF-Frameworks sind für die Verwendung der Werte SSL 3.0 und TLS 1.0 hartcodiert. Diese Werte können nicht geändert werden. Sie müssen auf .NET Framework 4.6 oder höhere Versionen aktualisieren und diese dann als Ziel wählen, um TLS 1.1 und 1.2 verwenden zu können.

## <a name="if-your-app-targets-net-framework-35"></a>Wenn Ihre App auf .NET Framework 3.5 abzielt

Wenn Sie explizit ein Sicherheitsprotokoll festlegen müssen, anstatt .NET-Framework oder das Betriebssystem das Sicherheitsprotokoll auswählen zu lassen, fügen Sie die Enumerationen `SecurityProtocolTypeExtensions` und `SslProtocolsExtension` zu Ihrem Code hinzu. `SecurityProtocolTypeExtensions` und `SslProtocolsExtension` enthalten Werte für `Tls12`, `Tls11` und den Wert `SystemDefault`. Siehe [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5 unter Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Konfigurieren der Sicherheit über AppContext-Switches (für .NET Framework 4.6 oder höhere Versionen)

Die in diesem Abschnitt beschriebenen [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Switches sind relevant, wenn Ihre App auf .NET Framework 4.6 oder höher abzielt und darunter ausgeführt wird. Ob standardmäßig oder explizit, die Switches sollten nach Möglichkeit auf `false` festgelegt sein. Wenn Sie die Sicherheitseinstellungen über einen oder beide Switches festlegen möchten, dann geben Sie in Ihrem Code keinen Wert für das Sicherheitsprotokoll an; dies würde die von den Switches vorgenommenen Einstellungen überschreiben.

Die Switches haben den gleichen Effekt, unabhängig davon, ob Sie HTTP-Netzwerke (<xref:System.Net.ServicePointManager>) oder TCP-Socketnetzwerke (<xref:System.Net.Security.SslStream>) betreiben.

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Der Wert `false` für `Switch.System.Net.DontEnableSchUseStrongCrypto` bewirkt, dass Ihre App starke Kryptographie verwendet. Durch den Wert `false` für `DontEnableSchUseStrongCrypto` werden sicherere Netzwerkprotokolle (TLS 1.2, TLS 1.1 und TLS 1.0) verwendet und nicht sichere Protokolle blockiert. Weitere Informationen finden Sie unter [Das Flag SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag). Ein Wert `true` deaktiviert eine starke Kryptographie für Ihre App.

Wenn Ihre App auf .NET Framework 4.6 oder höhere Versionen abzielt, wird dieser Switch standardmäßig auf `false` gesetzt. Das ist der empfohlene sichere Standard. Wenn Ihre App unter .NET Framework 4.6 ausgeführt wird, aber auf eine frühere Version abzielt, wird der Switch standardmäßig auf `true` gesetzt. In diesem Fall sollten Sie ihn explizit auf `false` setzen.

`DontEnableSchUseStrongCrypto` sollte nur dann den Wert `true` aufweisen, wenn Sie sich mit älteren Diensten verbinden müssen, die keine starke Kryptographie unterstützen und nicht aktualisiert werden können.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Der Wert `false` für `Switch.System.Net.DontEnableSystemDefaultTlsVersions` bewirkt, dass in Ihrer App das Protokoll vom Betriebssystem ausgewählt werden kann. Der Wert `true` bewirkt, dass Ihre App Protokolle verwendet, die vom .NET Framework ausgewählt wurden.

Wenn Ihre App unter .NET Framework 4.7 oder höhere Versionen abzielt, wird dieser Switch standardmäßig auf `false` gesetzt. Das ist der empfohlene sichere Standard. Wenn Ihre App unter .NET Framework 4.7 oder höheren Versionen ausgeführt wird, aber auf eine frühere Version abzielt, wird der Switch standardmäßig auf `true` gesetzt. In diesem Fall sollten Sie ihn explizit auf `false` setzen.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Der Wert `false` für `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` bewirkt, dass Ihre Anwendung den in `ServicePointManager.SecurityProtocols` definierten Wert für die Nachrichtensicherheit unter Verwendung von Zertifikatanmeldeinformationen verwendet. Durch den Wert `true` wird das höchste verfügbare Protokoll, bis zu TLS 1.0, verwendet.

Für Anwendungen, die auf .NET Framework 4.7 und höhere Versionen abzielen, wird dieser Wert standardmäßig auf `false` festgelegt. Für Anwendungen, die auf .NET Framework 4.6.2 und frühere Versionen abzielen, wird dieser Wert standardmäßig auf `true` festgelegt.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Der Wert `false` für `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` legt in der Standardkonfiguration fest, dass das Protokoll vom Betriebssystem ausgewählt werden kann. Der Wert `true` legt die Standardeinstellung auf das höchste verfügbare Protokoll, bis zu TLS 1.2, fest.

Für Anwendungen, die auf .NET Framework 4.7.1 und höhere Versionen abzielen, wird dieser Wert standardmäßig auf `false` festgelegt. Für Anwendungen, die auf .NET Framework 4.7 und frühere Versionen abzielen, wird dieser Wert standardmäßig auf `true` festgelegt.

Weitere Informationen über TLS-Protokolle finden Sie unter [Entschärfung: TLS-Protokolle](../migration-guide/mitigation-tls-protocols.md). Weitere Informationen über `AppContext`-Switches finden Sie unter [`<AppContextSwitchOverrides> Element`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Konfigurieren der Sicherheit über die Windows-Registrierung

> [!WARNING]
> Das Festlegen von Registrierungsschlüsseln betrifft alle Anwendungen auf dem System. Verwenden Sie diese Option nur, wenn Sie die vollständige Kontrolle über den Computer innehaben und die Änderungen an der Registrierung kontrollieren können.

Wenn die Einstellung mindestens eines `AppContext`-Switches nicht möglich ist, können Sie die Sicherheitsprotokolle für Ihre App mit den in diesem Abschnitt beschriebenen Windows-Registrierungsschlüsseln steuern. Möglicherweise können Sie einen oder beide `AppContext`-Switches nicht verwenden, wenn Ihre App unter .NET Framework-Version 4.5.2 oder früheren Versionen ausgeführt wird oder Sie die Konfigurationsdatei nicht bearbeiten können. Wenn Sie die Sicherheit mit der Registrierung konfigurieren möchten, geben Sie keinen Sicherheitsprotokollwert in Ihrem Code an; dies würde die Registrierungseinstellung außer Kraft setzen.

Die Namen der Registrierungsschlüssel ähneln den Namen der entsprechenden `AppContext`-Switches, jedoch ohne `DontEnable` vor dem Namen. Der `AppContext`-Switch `DontEnableSchUseStrongCrypto` ist beispielsweise der Registrierungsschlüssel [SchUseStrongCrypto](#schusestrongcrypto).

Diese Schlüssel sind in allen Versionen von .NET Framework verfügbar, für die es einen aktuellen Sicherheitspatch gibt. Siehe [Sicherheitsupdates](#security-updates).

Alle unten beschriebenen Registrierungsschlüssel haben den gleichen Effekt, unabhängig davon, ob Sie HTTP-Netzwerke (<xref:System.Net.ServicePointManager>) oder TCP-Socketnetzwerke (<xref:System.Net.Security.SslStream>) betreiben.

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

Der Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` hat einen Wert vom Typ DWORD. Der Wert 1 bewirkt, dass Ihre App eine starke Kryptographie verwendet. Bei der starken Kryptographie werden sicherere Netzwerkprotokolle (TLS 1.2, TLS 1.1 und TLS 1.0) verwendet und nicht sichere Protokolle blockiert. Der Wert 0 deaktiviert die starke Kryptographie. Weitere Informationen finden Sie unter [Das Flag SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag).

Wenn Ihre App unter .NET Framework 4.6 oder höhere Versionen abzielt, wird dieser Schlüssel standardmäßig auf 1 gesetzt. Das ist der empfohlene sichere Standard. Wenn Ihre App unter .NET Framework 4.6 ausgeführt wird, aber auf eine frühere Version abzielt, wird der Schlüssel standardmäßig auf 0 gesetzt. In diesem Fall sollten Sie dessen Wert explizit auf 1 setzen.

Dieser Schlüssel sollte nur dann den Wert 0 aufweisen, wenn Sie sich mit älteren Diensten verbinden müssen, die keine starke Kryptographie unterstützen und nicht aktualisiert werden können.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

Der Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` hat einen Wert vom Typ DWORD. Der Wert 1 bewirkt, dass in Ihrer App das Protokoll vom Betriebssystem ausgewählt werden kann. Der Wert 0 bewirkt, dass Ihre App Protokolle verwendet, die vom .NET Framework ausgewählt wurden.

`<VERSION>` muss v4.0.30319 (für .NET Framework 4 und höher) oder v2.0.50727 (für .NET Framework 3.5) sein.

Wenn Ihre App unter .NET Framework 4.7 oder höhere Versionen abzielt, wird dieser Schlüssel standardmäßig auf 1 gesetzt. Das ist der empfohlene sichere Standard. Wenn Ihre App unter .NET Framework 4.7 oder höheren Versionen ausgeführt wird, aber auf eine frühere Version abzielt, wird der Schlüssel standardmäßig auf 0 gesetzt. In diesem Fall sollten Sie dessen Wert explizit auf 1 setzen.

Weitere Informationen finden Sie unter [Kumulatives Update für Windows 10 Version 1511 und Windows Server 2016 Technical Preview 4: 10. Mai 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Weitere Informationen für die Verwendung mit .NET Framework 3.5.1 finden Sie unter [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5.1 unter Windows 7 SP1 und Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

Die folgende _.REG_-Datei legt die Registrierungsschlüssel und deren Varianten auf die sichersten Werte fest:

```text
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

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Konfigurieren von Schannel-Protokollen in der Windows-Registrierung

Sie können die Registrierung verwenden, um die Protokolle, die Ihre Client- und/oder Server-App aushandelt, genau zu steuern. Die Vernetzung Ihrer App erfolgt über Schannel (eine andere Bezeichnung für [Secure Channel](/windows/desktop/SecAuthN/secure-channel)). Durch die Konfiguration von `Schannel` können Sie das Verhalten Ihrer App konfigurieren.

Beginnen Sie mit dem Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols`. Unter diesem Schlüssel können Sie beliebige Unterschlüssel im Satz `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1` und `TLS 1.2` anlegen. Unter jedem dieser Unterschlüssel können Sie die Unterschlüssel `Client` und/oder `Server` anlegen. Unter `Client` und `Server` können Sie die DWORD-Werte `DisabledByDefault` (0 oder 1) und `Enabled` (0 oder 0xFFFFFFFF) anlegen.

## <a name="the-sch_use_strong_crypto-flag"></a>Das Flag SCH_USE_STRONG_CRYPTO

Wenn es aktiviert ist (standardmäßig durch einen `AppContext`-Switch oder durch die Windows-Registrierung), verwendet .NET Framework das Flag `SCH_USE_STRONG_CRYPTO`, wenn Ihre App ein TLS-Sicherheitsprotokoll anfordert. Das Flag `SCH_USE_STRONG_CRYPTO` kann standardmäßig mit dem `AppContext`-Switch oder mit der Registrierung aktiviert werden. Das Betriebssystem übergibt das Flag an `Schannel` und weist es an, bekannte schwache Kryptografiealgorithmen, Verschlüsselungssuiten und TLS/SSL-Protokollversionen zu deaktivieren, die andernfalls für eine bessere Interoperabilität aktiviert werden könnten. Weitere Informationen finden Sie unter:

- [Secure Channel](/windows/desktop/SecAuthN/secure-channel)
- [SCHANNEL_CRED-Struktur](/windows/win32/api/schannel/ns-schannel-schannel_cred)

Das Flag `SCH_USE_STRONG_CRYPTO` wird ebenfalls an `Schannel` übergeben, wenn Sie explizit die Enumerationswerte `Tls` (TLS 1.0), `Tls11` oder `Tls12` von <xref:System.Net.SecurityProtocolType> oder <xref:System.Security.Authentication.SslProtocols> verwenden.

## <a name="security-updates"></a>Sicherheitsupdates

Die bewährten Methoden in diesem Artikel hängen von der Installation aktueller Sicherheitsupdates ab. Diese Updates beinhalten die Möglichkeit, erweiterte Features von .NET Framework 4.7 und höher zu verwenden. Aktuelle Sicherheitsupdates sind wichtig, wenn Ihre App unter .NET Framework 4.7 und höheren Versionen läuft (auch wenn sie auf eine frühere Version abzielt).

Um .NET Framework zu aktualisieren, damit das Betriebssystem die beste Version von TLS verwenden kann, müssen mindestens folgende Installationsanforderungen erfüllt sein:

- Die [Vorschauversion des Qualitätsrollups für .NET Framework vom August 2017](https://devblogs.microsoft.com/dotnet/net-framework-august-2017-preview-of-quality-rollup/)
- **Oder** das [Sicherheits- und Qualitätsrollup für .NET Framework vom September 2017](https://devblogs.microsoft.com/dotnet/net-framework-september-2017-security-and-quality-rollup/)

Siehe auch:

- [.NET Framework-Versionen und -Abhängigkeiten](../migration-guide/versions-and-dependencies.md)
- [Vorgehensweise: Determine Which .NET Framework Versions Are Installed](../migration-guide/how-to-determine-which-versions-are-installed.md) (Bestimmen der installierten .NET Framework-Versionen).

## <a name="support-for-tls-12"></a>Unterstützung für TLS 1.2

Damit Ihre App TLS 1.2 aushandeln kann, müssen sowohl das Betriebssystem als auch die .NET Framework-Version TLS 1.2 unterstützen.

**Betriebssystemanforderungen zur Unterstützung von TLS 1.2**

Um TLS 1.2 und/oder TLS 1.1 auf einem System, das sie unterstützt, zu aktivieren oder erneut zu aktivieren, siehe [Transport Layer Security (TLS)-Registrierungseinstellungen](/windows-server/security/tls/tls-registry-settings).

| **Betriebssystem** | **TLS 1.2-Unterstützung** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | Unterstützt und standardmäßig aktiviert. |
| Windows 8.1<br>Windows Server 2012 R2 | Unterstützt und standardmäßig aktiviert. |
| Windows 8.0<br>Windows Server 2012 | Unterstützt und standardmäßig aktiviert. |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | Unterstützt und nicht standardmäßig aktiviert. Weitere Informationen zum Aktivieren von TLS 1.2 finden Sie auf der Webseite [Transport Layer Security (TLS)-Registrierungseinstellungen](/windows-server/security/tls/tls-registry-settings). |
| Windows Server 2008 | Für Unterstützung für TLS 1.2 und TLS 1.1 ist ein Update erforderlich. Siehe [Update zum Hinzufügen der Unterstützung von TLS 1.1 und TLS 1.2 in Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | Wird nicht unterstützt. |

Informationen darüber, welche TLS/SSL-Protokolle auf den einzelnen Windows-Version standardmäßig aktiviert sind, finden Sie unter [Protokolle in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).

**Anforderungen zur Unterstützung von TLS 1.2 mit .NET Framework 3.5**

Diese Tabelle zeigt das Betriebssystemupdate, das Sie benötigen, um TLS 1.2 mit .NET Framework 3.5 zu unterstützen. Es wird empfohlen, alle Betriebssystemupdates zu installieren.

| **Betriebssystem** | **Erforderliches Mindestupdate zur Unterstützung von TLS 1.2 mit .NET Framework 3.5** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | [Kumulatives Update für Windows 10 Version 1511 und Windows Server 2016 Technical Preview 4: 10. Mai 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1<br>Windows Server 2012 R2 | [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5 unter Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0<br>Windows Server 2012 | [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5 unter Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 3.5.1 unter Windows 7 SP1 und Windows Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Unterstützung für Standardversionen des TLS-Systems im .NET Framework 2.0 SP2 unter Windows Vista SP2 und Windows Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Nicht unterstützt |

## <a name="azure-cloud-services"></a>Azure Cloud Services

Wenn Sie Web- und Workerrollen von [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) zum Hosten und Ausführen Ihrer Anwendung verwenden, gibt es einige Aspekte, die Sie für die Unterstützung von TLS 1.2 berücksichtigen müssen.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>.NET Framework 4.7 ist nicht standardmäßig auf dem Azure-Gastbetriebssystem installiert

In der aktuellen Version der Azure-Gastbetriebssystemfamilie 5 (Windows Server 2016) ist die neueste Version 4.6.2 installiert. Um zu sehen, welche Versionen von .NET Framework auf jedem Azure-Gastbetriebssystem installiert sind, lesen Sie die [Azure-Gastbetriebssystemversionen und SDK-Kompatibilitätsmatrix](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Wenn Ihre App auf eine .NET Framework-Version abzielt, die in der Azure-Gastbetriebssystemversion nicht verfügbar ist, dann müssen Sie diese selbst installieren. Siehe [Installieren von .NET in Rollen in Azure Cloud Services](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Wenn die Framework-Installation einen Neustart erfordert, können auch die Dienstrollen neu gestartet werden, bevor sie in den Bereit-Zustand versetzt werden.

### <a name="azure-guest-os-registry-settings"></a>Registrierungseinstellungen für das Azure-Gastbetriebssystem

Das Image der Azure-Gastbetriebssystem-Familie 5 für [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) hat bereits den Registrierungsschlüssel `SchUseStrongCrypto` auf den Wert „1“ festgelegt. Weitere Informationen finden Sie unter [SchUseStrongCrypto](#schusestrongcrypto).

Legen Sie den Registrierungsschlüssel [SystemDefaultTlsVersions](#systemdefaulttlsversions) auf 1 fest. Siehe [Konfigurieren der Sicherheit über die Windows-Registrierung](#configuring-security-via-the-windows-registry).
