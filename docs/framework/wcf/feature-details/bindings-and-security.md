---
title: Bindungen und Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 5e3a8bc58d0828f50feb7752eb438d41695460fa
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611905"
---
# <a name="bindings-and-security"></a>Bindungen und Sicherheit
Die vom System bereitgestellten Bindungen mit Windows Communication Foundation (WCF) bieten eine schnelle Möglichkeit zum Programmieren von WCF-Anwendungen. Mit einer Ausnahme haben alle Bindungen ein standardmäßig aktiviertes Sicherheitsschema. Dieses Thema hilft Ihnen, die richtige Bindung für die benötigte Sicherheit auszuwählen.  
  
 Eine Übersicht über WCF-Sicherheit, finden Sie unter [Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/security-overview.md). Weitere Informationen zum Verwenden von Bindungen, WCF-Programmierung finden Sie unter [Programmieren der WCF-Sicherheit](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).  
  
 Wenn Sie bereits eine Bindung ausgewählt haben, finden Sie weitere Informationen zu den Laufzeitverhalten, die Sicherheit in zugeordnet sind [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
 Einige Sicherheitsfunktionen sind mit den vom System bereitgestellten Bindungen nicht programmierbar. Mehr Kontrolle, die mit einer benutzerdefinierten Bindung, finden Sie unter [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).  
  
## <a name="security-functions-of-bindings"></a>Sicherheitsfunktionen von Bindungen  
 WCF umfasst eine Anzahl von vom System bereitgestellten Bindungen, die meisten Anforderungen erfüllen. Wenn eine bestimmte Bindung nicht ausreicht, können Sie auch eine benutzerdefinierte Bindung erstellen. Eine Liste der vom System bereitgestellten Bindungen, finden Sie unter [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md). Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Jede Bindung in WCF hat zwei Formen: als API- und als XML-Element in einer Konfigurationsdatei verwendet. Z. B. die `WSHttpBinding` (API) verfügt über eine Entsprechung in der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 Der folgende Abschnitt führt beide Formen einer Bindung auf und fasst die Sicherheitsfunktionen zusammen.  
  
### <a name="basichttp"></a>BasicHttp  
 Verwenden Sie im Code die <xref:System.ServiceModel.BasicHttpBinding> Klasse; verwenden Sie in der Konfiguration der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 Diese Bindung ist für die Verwendung mit vielen verschiedenen vorhandenen Technologien vorgesehen, u. a. mit:  
  
-   ASP.NET-Webdienste (ASMX), Version 1.  
  
-   Webdienststeigerungen (WSE)-Anwendungen.  
  
-   Grundlegendes Profil gemäß der Webdienst-Interoperabilitätsspezifikation (WS-I) Spezifikation (<https://go.microsoft.com/fwlink/?LinkId=38955>).  
  
-   Standardsicherheitsprofil gemäß der Definition in WS-I.  
  
 Standardmäßig ist diese Bindung nicht sicher. Sie ist darauf ausgelegt, mit ASMX-Diensten zusammenzuarbeiten. Wenn die Sicherheit aktiviert ist, ist die Bindung für eine nahtlose Interoperabilität mit Internet Information Services (IIS)-Sicherheitsmechanismen ausgelegt, z. B. Standardauthentifizierung, Hashwert und integrierte Windows-Sicherheit. Weitere Informationen finden Sie unter [Transport Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/transport-security-overview.md). Diese Bindung unterstützt Folgendes:  
  
-   HTTPS-Transportsicherheit.  
  
-   HTTP-Standardauthentifizierung  
  
-   WS-Sicherheit.  
  
 Weitere Informationen finden Sie unter<xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>und <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
### <a name="wshttpbinding"></a>WSHttpBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.WSHttpBinding> Klasse; verwenden Sie in der Konfiguration der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 Standardmäßig implementiert diese Bindung die WS-Sicherheitsspezifikation und bietet Interoperabilität mit Diensten, die die WS-*-Spezifikationen implementieren. Sie unterstützt Folgendes:  
  
-   HTTPS-Transportsicherheit.  
  
-   WS-Sicherheit.  
  
-   HTTPS-Transportschutz mit SOAP-Nachrichten-Anmeldeinformationen-Sicherheit zur Authentifizierung des Anrufers.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, und <xref:System.ServiceModel.HttpProxyCredentialType>.  
  
### <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.WSDualHttpBinding> Klasse; verwenden Sie in der Konfiguration der [ \<WsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).  
  
 Diese Bindung wird entworfen, um Duplexdienstanwendungen zu aktivieren. Diese Bindung implementiert die WS-Sicherheitsspezifikation für nachrichtenbasierte Übertragungssicherheit. Transportsicherheit ist nicht verfügbar. Standardmäßig gibt es die folgenden Funktionen:  
  
-   Implementiert WS-Reliable Messaging für Zuverlässigkeit.  
  
-   Implementiert WS-Sicherheit für die Übertragungssicherheit und zur Authentifizierung.  
  
-   Verwendet HTTP zur Nachrichtenübermittlung.  
  
-   Verwendet Text/XML-Nachrichtencodierung.  
  
 Beim Verwenden von WS-Sicherheit (Nachrichtenebenen-Sicherheit) ermöglicht die Bindung die Konfiguration der folgenden Parameter:  
  
-   der Sicherheitsalgorithmus-Suite, um den Kryptografiesatz zu bestimmen.  
  
-   Bindungsoptionen für Folgendes:  
  
    -   die Bereitstellung von Dienstanmeldeinformationen, die beim Client Out-of-Band verfügbar sind.  
  
    -   die Bereitstellung von vom Dienst als Teil des Kanal-Setups ausgehandelten Dienstanmeldeinformationen.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.WSDualHttpSecurity> und <xref:System.ServiceModel.WSDualHttpSecurityMode>.  
  
### <a name="nettcpbinding"></a>NetTcpBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.NetTcpBinding> Klasse; verwenden Sie in der Konfiguration der [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 Diese Bindung ist für die computerübergreifende Kommunikation optimiert. Standardmäßig besitzt sie folgende Eigenschaften:  
  
-   Implementiert Transport Layer Security.  
  
-   Setzt Windows-Sicherheit für die Übertragungssicherheit und zur Authentifizierung ein.  
  
-   Verwendet TCP für Transport.  
  
-   Implementiert binäre Nachrichtencodierung.  
  
-   Implementiert WS-Reliable Messaging.  
  
 Es gibt folgende Optionen:  
  
-   Nachrichtenebenen-Sicherheit (über WS-Sicherheit).  
  
-   Transportsicherheit mit Nachrichtenanmeldeinformationen: Vertraulichkeit und Integrität werden über Transport Layer Security (TLS) über TCP geboten und die Anmeldeinformationen für die Authentifizierung über WS-Sicherheit.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, und <xref:System.ServiceModel.MessageCredentialType>.  
  
### <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.NetNamedPipeBinding> Klasse; verwenden Sie in der Konfiguration der [ \<NetNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).  
  
 Diese Bindung ist für prozessübergreifende Kommunikation (normalerweise auf dem gleichen Computer) optimiert. Standardmäßig besitzt diese Bindung folgende Eigenschaften:  
  
-   Verwendet Transportsicherheit für die Nachrichtenübertragung und zur Authentifizierung.  
  
-   Verwendet Named Pipes zur Nachrichtenübermittlung.  
  
-   Implementiert binäre Nachrichtencodierung.  
  
-   Verschlüsselung und Nachrichtensignierung.  
  
 Es gibt folgende Optionen:  
  
-   Authentifizierung über Windows-Sicherheit.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> und <xref:System.ServiceModel.NamedPipeTransportSecurity>.  
  
### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> Klasse; verwenden Sie in der Konfiguration der [ \<MsmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).  
  
 Diese Bindung ist optimiert, für das Erstellen von WCF-Clients und Diensten, die Zusammenwirken mit nicht - WCF MSMQ Microsoft Message Queuing-Endpunkten.  
  
 Standardmäßig verwendet diese Bindung Transportsicherheit und stellt die folgenden Sicherheitseigenschaften bereit:  
  
-   Sicherheit kann deaktiviert werden (Keine).  
  
-   MSMQ-Transportsicherheit (Transport).  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.NetMsmqSecurity> und <xref:System.ServiceModel.NetMsmqSecurityMode>.  
  
### <a name="netmsmqbinding"></a>NetMsmqBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.NetMsmqBinding> Klasse; verwenden Sie in der Konfiguration der [ \<NetMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).  
  
 Diese Bindung dient zur Verwendung beim Erstellen von WCF-Diensten, die MSMQ benötigen Unterstützung für Nachrichten in Warteschlange.  
  
 Standardmäßig verwendet diese Bindung Transportsicherheit und stellt die folgenden Sicherheitseigenschaften bereit:  
  
-   Sicherheit kann deaktiviert werden (Keine).  
  
-   MSMQ-Transportsicherheit (Transport).  
  
-   SOAP-basierte Nachrichtensicherheit (Nachricht).  
  
-   Gleichzeitige Transport- und Nachrichtensicherheit (Beides).  
  
-   Unterstützte Typen von Clientanmeldeinformationen: Keine, Windows, UserName, Zertifikat, IssuedToken.  
  
 Die <xref:System.ServiceModel.MessageCredentialType.Certificate>-Anmeldeinformationen werden nur unterstützt, wenn der Sicherheitsmodus entweder auf <xref:System.ServiceModel.NetMsmqSecurityMode.Both> oder auf <xref:System.ServiceModel.NetMsmqSecurityMode.Message> festgelegt ist.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.MessageSecurityOverMsmq> und <xref:System.ServiceModel.MsmqTransportSecurity>.  
  
### <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 Verwenden Sie im Code die <xref:System.ServiceModel.WSFederationHttpBinding> Klasse; verwenden Sie in der Konfiguration der [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
 Standardmäßig verwendet diese Bindung WS-Sicherheit (Nachrichtenebenen-Sicherheit).  
  
 Weitere Informationen finden Sie unter [Verbund](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, und <xref:System.ServiceModel.WSFederationHttpSecurityMode>.  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen  
 Wenn keine der vom System bereitgestellten Bindungen Ihre Anforderungen erfüllt, können Sie eine benutzerdefinierte Bindung mit einem benutzerdefinierten Sicherheitsbindungselement erstellen. Weitere Informationen finden Sie unter [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).  
  
## <a name="binding-choices"></a>Bindungsmöglichkeiten  
 In der folgenden Tabelle werden die Funktionen aufgeführt, die in der Sicherheitsmoduseinstellung geboten werden, d. h. die Funktionen werden aufgeführt, die bei Festlegung des Sicherheitsmodus auf `Transport`, `Message` oder `TransportWithMessageCredential` verfügbar sind. Verwenden Sie diese Tabelle, um die Sicherheitsfunktionen zu finden, die von der Anwendung benötigt werden.  
  
|Einstellung|Features|  
|-------------|--------------|  
|Transport|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> Point-to-Point-Sicherheit<br /><br /> Interoperabilität<br /><br /> Hardwarebeschleunigung.<br /><br /> Hoher Durchsatz<br /><br /> Sichere Firewall<br /><br /> Hohe-Wartezeit-Anwendungen<br /><br /> Wiederverschlüsselung über mehrere Hops|  
|Meldung|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> End-to-End-Sicherheit<br /><br /> Interoperabilität<br /><br /> Rich Claims<br /><br /> Verbund<br /><br /> Mehrfaktoren-Authentifizierung<br /><br /> Benutzerdefinierte Token<br /><br /> Notar-/Timestampdienst<br /><br /> Hohe-Wartezeit-Anwendungen<br /><br /> Beständigkeit von Nachrichtensignaturen|  
|TransportWithMessageCredential|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> Point-to-Point-Sicherheit<br /><br /> Interoperabilität<br /><br /> Hardwarebeschleunigung.<br /><br /> Hoher Durchsatz<br /><br /> Rich Client-Claims<br /><br /> Verbund<br /><br /> Mehrfaktoren-Authentifizierung<br /><br /> Benutzerdefinierte Token<br /><br /> Sichere Firewall<br /><br /> Hohe-Wartezeit-Anwendungen<br /><br /> Wiederverschlüsselung über mehrere Hops|  
  
 In der folgenden Tabelle werden die Bindungen aufgeführt, die die verschiedenen Moduseinstellungen unterstützen. Wählen Sie eine Bindung aus der Tabelle aus, die verwendet werden soll, um den Dienstendpunkt zu erstellen.  
  
|Bindung|Transportmodus-Support|Nachrichtenmodus-Support|TransportWithMessageCredential-Unterstützung|  
|-------------|----------------------------|--------------------------|--------------------------------------------|  
|`BasicHttpBinding`|Ja|Ja|Ja|  
|`WSHttpBinding`|Ja|Ja|Ja|  
|`WSDualHttpBinding`|Nein|Ja|Nein|  
|`NetTcpBinding`|Ja|Ja|Ja|  
|`NetNamedPipeBinding`|Ja|Nein|Nein|  
|`NetMsmqBinding`|Ja|Ja|Nein|  
|`MsmqIntegrationBinding`|Ja|Nein|Nein|  
|`wsFederationHttpBinding`|Nein|Ja|Ja|  
  
## <a name="transport-credentials-in-bindings"></a>Transportieren von Anmeldeinformationen in Bindungen  
 In der folgenden Tabelle werden die Typen von Clientanmeldeinformationen aufgeführt, die bei der Nutzung von `BasicHttpBinding` oder `WSHttpBinding` im Transportsicherheitsmodus zur Verfügung stehen.  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|Keiner|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Standard|Standardauthentifizierung. Weitere Informationen finden Sie unter RFC 2617 – HTTP Authentication: Grundlegende und Digestauthentifizierung, verfügbar unter <https://go.microsoft.com/fwlink/?LinkId=84023>.|  
|Digest|Hashwertauthentifizierung. Weitere Informationen finden Sie unter RFC 2617 – HTTP Authentication: Grundlegende und Digestauthentifizierung, verfügbar unter <https://go.microsoft.com/fwlink/?LinkId=84023>.|  
|NTLM|NT-LAN-Manager (NTLM)-Authentifizierung.|  
|Windows|Windows-Authentifizierung.|  
|Zertifikat|Die Authentifizierung fand über ein Zertifikat statt.|  
|IssuedToken|Ermöglicht dem Dienst die Forderung, dass der Client über ein Token, das von einem Sicherheitstokendienst oder von [!INCLUDE[infocard](../../../../includes/infocard-md.md)] ausgestellt wurde, authentifiziert werden muss. Weitere Informationen finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
### <a name="message-client-credentials-in-bindings"></a>Clientanmeldeinformationen für Nachrichten in Bindungen  
 In der folgenden Tabelle werden die Typen von Clientanmeldeinformationen aufgeführt, die bei der Nutzung einer Bindung im Nachrichtensicherheitsmodus zur Verfügung stehen.  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|Keiner|Ermöglicht dem Dienst die Interaktion mit anonymen Clients.|  
|Windows|Ermöglicht SOAP-Nachrichtenaustausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen.|  
|UserName|Ermöglicht dem Dienst die Forderung an den Client, sich über eine Benutzernamen-Anmeldeinformation zu authentifizieren. Beachten Sie, dass, wenn der Sicherheitsmodus, um festgelegt ist `TransportWithMessageCredential`, WCF unterstützt das Senden eines kennwortdigests oder das Ableiten von Schlüsseln anhand des Kennworts und die Verwendung solcher Schlüssel für die nachrichtenmodussicherheit nicht. Daher setzt WCF an, dass der Transport geschützt wird, wenn der Identitätsnachweis über den Benutzernamen.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss.|  
|IssuedToken|Ermöglicht es dem Dienst, einen Sicherheitstokendienst zu verwenden, um ein benutzerdefiniertes Token zu liefern.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Ausählen eines Anmeldeinformationentyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
