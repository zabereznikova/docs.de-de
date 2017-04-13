---
title: "Bindungen und Sicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bindungen [WCF]"
  - "Bindungen [WCF], Sicherheit"
  - "WCF-Sicherheit"
  - "Windows Communication Foundation, Sicherheit"
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
caps.latest.revision: 42
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 42
---
# Bindungen und Sicherheit
Die vom System bereitgestellten, in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] integrierten Bindungen bieten eine schnelle Möglichkeit, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen zu programmieren.Mit einer Ausnahme haben alle Bindungen ein standardmäßig aktiviertes Sicherheitsschema.Dieses Thema hilft Ihnen, die richtige Bindung für die benötigte Sicherheit auszuwählen.  
  
 Eine Übersicht über die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheit finden Sie unter [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Programmierung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit Bindungen finden Sie unter [Programmieren der WCF\-Sicherheit](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).  
  
 Wenn Sie bereits eine Bindung ausgewählt haben, können Sie unter [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md) mehr über die der Sicherheit zugehörigen Laufzeitverhalten erfahren.  
  
 Einige Sicherheitsfunktionen sind mit den vom System bereitgestellten Bindungen nicht programmierbar.Weitere Informationen über die Kontrolle durch benutzerdefinierte Bindungen finden Sie unter [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
## Sicherheitsfunktionen von Bindungen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet einige vom System bereitgestellte Bindungen, die die meisten Bedürfnisse erfüllen.Wenn eine bestimmte Bindung nicht ausreicht, können Sie auch eine benutzerdefinierte Bindung erstellen.Eine Liste der vom System bereitgestellten Bindungen finden Sie unter [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu benutzerdefinierten Bindungen finden Sie unter [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Jede Bindung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erscheint in zwei Formen: als API\- und als XML\-Element, die in einer Konfigurationsdatei verwendet werden.`WSHttpBinding` \(API\) hat z. B. in [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) ein Äquivalent.  
  
 Der folgende Abschnitt führt beide Formen einer Bindung auf und fasst die Sicherheitsfunktionen zusammen.  
  
### BasicHttp  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.BasicHttpBinding>; verwenden Sie in der Konfiguration [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 Diese Bindung ist für die Verwendung mit vielen verschiedenen vorhandenen Technologien vorgesehen, u. a. mit:  
  
-   ASP.NET\-Webdienste \(ASMX\), Version 1.  
  
-   Webdienststeigerungen \(WSE\)\-Anwendungen.  
  
-   Grundlegendes Profil gemäß der Webdienst\-Interoperabilitätsspezifikation \(WS\-I\) \([http:\/\/go.microsoft.com\/fwlink\/?LinkId\=38955](http://go.microsoft.com/fwlink/?LinkId=38955) \(möglicherweise in englischer Sprache\)\).  
  
-   Standardsicherheitsprofil gemäß der Definition in WS\-I.  
  
 Standardmäßig ist diese Bindung nicht sicher.Sie ist darauf ausgelegt, mit ASMX\-Diensten zusammenzuarbeiten.Wenn die Sicherheit aktiviert ist, ist die Bindung für eine nahtlose Interoperabilität mit Internet Information Services \(IIS\)\-Sicherheitsmechanismen ausgelegt, z. B. Standardauthentifizierung, Digest und integrierte Windows\-Sicherheit.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Übersicht über die Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).Diese Bindung unterstützt Folgendes:  
  
-   HTTPS\-Transportsicherheit.  
  
-   HTTP\-Standardauthentifizierung  
  
-   WS\-Sicherheit.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> und <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
### WSHttpBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.WSHttpBinding>; verwenden Sie in der Konfiguration [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 Standardmäßig implementiert diese Bindung die WS\-Sicherheitsspezifikation und bietet Interoperabilität mit Diensten, die die WS\-\*\-Spezifikationen  implementieren.Sie unterstützt Folgendes:  
  
-   HTTPS\-Transportsicherheit.  
  
-   WS\-Sicherheit.  
  
-   HTTPS\-Transportschutz mit SOAP\-Nachrichten\-Anmeldeinformationen\-Sicherheit zur Authentifizierung des Anrufers.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType> und <xref:System.ServiceModel.HttpProxyCredentialType>.  
  
### WSDualHttpBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.WSDualHttpBinding>; verwenden Sie in der Konfiguration [\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).  
  
 Diese Bindung wird entworfen, um Duplexdienstanwendungen zu aktivieren.Diese Bindung implementiert die WS\-Sicherheitsspezifikation für nachrichtenbasierte Übertragungssicherheit.Transportsicherheit ist nicht verfügbar.Standardmäßig gibt es die folgenden Funktionen:  
  
-   Implementiert WS\-Reliable Messaging für Zuverlässigkeit.  
  
-   Implementiert WS\-Sicherheit für die Übertragungssicherheit und zur Authentifizierung.  
  
-   Verwendet HTTP zur Nachrichtenübermittlung.  
  
-   Verwendet Text\/XML\-Nachrichtencodierung.  
  
 Beim Verwenden von WS\-Sicherheit \(Nachrichtenebenen\-Sicherheit\) ermöglicht die Bindung die Konfiguration der folgenden Parameter:  
  
-   der Sicherheitsalgorithmus\-Suite, um den Kryptografiesatz zu bestimmen.  
  
-   Bindungsoptionen für Folgendes:  
  
    -   die Bereitstellung von Dienstanmeldeinformationen, die beim Client Out\-of\-Band verfügbar sind.  
  
    -   die Bereitstellung von vom Dienst als Teil des Kanal\-Setups ausgehandelten Dienstanmeldeinformationen.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.WSDualHttpSecurity> und <xref:System.ServiceModel.WSDualHttpSecurityMode>.  
  
### NetTcpBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.NetTcpBinding>; verwenden Sie in der Konfiguration [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 Diese Bindung ist für die computerübergreifende Kommunikation optimiert.Standardmäßig besitzt sie folgende Eigenschaften:  
  
-   Implementiert Transport Layer Security.  
  
-   Setzt Windows\-Sicherheit für die Übertragungssicherheit und zur Authentifizierung ein.  
  
-   Verwendet TCP für Transport.  
  
-   Implementiert binäre Nachrichtencodierung.  
  
-   Implementiert WS\-Reliable Messaging.  
  
 Es gibt folgende Optionen:  
  
-   Nachrichtenebenen\-Sicherheit \(über WS\-Sicherheit\).  
  
-   Transportsicherheit mit Nachrichtenanmeldeinformationen: Vertraulichkeit und Integrität werden über Transport Layer Security \(TLS\) über TCP geboten und die Anmeldeinformationen für die Authentifizierung über WS\-Sicherheit.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp> und <xref:System.ServiceModel.MessageCredentialType>.  
  
### NetNamedPipeBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.NetNamedPipeBinding>; verwenden Sie in der Konfiguration [\<netNamedPipeBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).  
  
 Diese Bindung ist für prozessübergreifende Kommunikation \(normalerweise auf dem gleichen Computer\) optimiert.Standardmäßig besitzt diese Bindung folgende Eigenschaften:  
  
-   Verwendet Transportsicherheit für die Nachrichtenübertragung und zur Authentifizierung.  
  
-   Verwendet Named Pipes zur Nachrichtenübermittlung.  
  
-   Implementiert binäre Nachrichtencodierung.  
  
-   Verschlüsselung und Nachrichtensignierung.  
  
 Es gibt folgende Optionen:  
  
-   Authentifizierung über Windows\-Sicherheit.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> und <xref:System.ServiceModel.NamedPipeTransportSecurity>.  
  
### MsmqIntegrationBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>; verwenden Sie in der Konfiguration [\<msmqIntegrationBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).  
  
 Diese Bindung ist für das Erstellen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients und \-Diensten optimiert, die mit Nicht\-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Microsoft Message Queuing \(MSMQ\)\-Endpunkten zusammenarbeiten.  
  
 Standardmäßig verwendet diese Bindung Transportsicherheit und stellt die folgenden Sicherheitseigenschaften bereit:  
  
-   Sicherheit kann deaktiviert werden \(Keine\).  
  
-   MSMQ\-Transportsicherheit \(Transport\).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.NetMsmqSecurity> und <xref:System.ServiceModel.NetMsmqSecurityMode>.  
  
### NetMsmqBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.NetMsmqBinding>; verwenden Sie in der Konfiguration [\<NetMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).  
  
 Diese Bindung ist für den Einsatz beim Erstellen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten gedacht, die MSMQ Queued Message\-Support benötigen.  
  
 Standardmäßig verwendet diese Bindung Transportsicherheit und stellt die folgenden Sicherheitseigenschaften bereit:  
  
-   Sicherheit kann deaktiviert werden \(Keine\).  
  
-   MSMQ\-Transportsicherheit \(Transport\).  
  
-   SOAP\-basierte Nachrichtensicherheit \(Nachricht\).  
  
-   Gleichzeitige Transport\- und Nachrichtensicherheit \(Beides\).  
  
-   Unterstützte Typen von Clientanmeldeinformationen: Keine, Windows, UserName, Zertifikat, IssuedToken.  
  
 Die <xref:System.ServiceModel.MessageCredentialType>\-Anmeldeinformationen werden nur unterstützt, wenn der Sicherheitsmodus entweder auf <xref:System.ServiceModel.NetMsmqSecurityMode> oder auf <xref:System.ServiceModel.NetMsmqSecurityMode> festgelegt ist.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.MessageSecurityOverMsmq> und <xref:System.ServiceModel.MsmqTransportSecurity>.  
  
### WSFederationHttpBinding  
 Verwenden Sie im Code die Klasse <xref:System.ServiceModel.WSFederationHttpBinding>; verwenden Sie in der Konfiguration [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
 Standardmäßig verwendet diese Bindung WS\-Sicherheit \(Nachrichtenebenen\-Sicherheit\).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Verbund](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity> und <xref:System.ServiceModel.WSFederationHttpSecurityMode>.  
  
## Benutzerdefinierte Bindungen  
 Wenn keine der vom System bereitgestellten Bindungen Ihre Anforderungen erfüllt, können Sie eine benutzerdefinierte Bindung mit einem benutzerdefinierten Sicherheitsbindungselement erstellen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).  
  
## Bindungsmöglichkeiten  
 In der folgenden Tabelle werden die Funktionen aufgeführt, die in der Sicherheitsmoduseinstellung geboten werden, d. h. die Funktionen werden aufgeführt, die bei Festlegung des Sicherheitsmodus auf `Transport`, `Message` oder `TransportWithMessageCredential` verfügbar sind.Verwenden Sie diese Tabelle, um die Sicherheitsfunktionen zu finden, die von der Anwendung benötigt werden.  
  
|Einstellung|Funktionen|  
|-----------------|----------------|  
|Transport|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> Point\-to\-Point\-Sicherheit<br /><br /> Interoperabilität<br /><br /> Hardwarebeschleunigung.<br /><br /> Hoher Durchsatz<br /><br /> Sichere Firewall<br /><br /> Hohe\-Wartezeit\-Anwendungen<br /><br /> Wiederverschlüsselung über mehrere Hops|  
|Nachricht|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> End\-to\-End\-Sicherheit<br /><br /> Interoperabilität<br /><br /> Rich Claims<br /><br /> Verbund<br /><br /> Mehrfaktoren\-Authentifizierung<br /><br /> Benutzerdefinierte Token<br /><br /> Notar\-\/Timestampdienst<br /><br /> Hohe\-Wartezeit\-Anwendungen<br /><br /> Beständigkeit von Nachrichtensignaturen|  
|TransportWithMessageCredential|Serverauthentifizierung<br /><br /> Clientauthentifizierung<br /><br /> Point\-to\-Point\-Sicherheit<br /><br /> Interoperabilität<br /><br /> Hardwarebeschleunigung.<br /><br /> Hoher Durchsatz<br /><br /> Rich Client\-Claims<br /><br /> Verbund<br /><br /> Mehrfaktoren\-Authentifizierung<br /><br /> Benutzerdefinierte Token<br /><br /> Sichere Firewall<br /><br /> Hohe\-Wartezeit\-Anwendungen<br /><br /> Wiederverschlüsselung über mehrere Hops|  
  
 In der folgenden Tabelle werden die Bindungen, die die verschiedenen Moduseinstellungen unterstützen, aufgeführt.Wählen Sie eine Bindung aus der Tabelle aus, die verwendet werden soll, um den Dienstendpunkt zu erstellen.  
  
|Bindung|Transportmodus\-Support|Nachrichtenmodus\-Support|TransportWithMessageCredential\-Unterstützung|  
|-------------|-----------------------------|-------------------------------|---------------------------------------------------|  
|`BasicHttpBinding`|Ja|Ja|Ja|  
|`WSHttpBinding`|Ja|Ja|Ja|  
|`WSDualHttpBinding`|Nein|Ja|Nein|  
|`NetTcpBinding`|Ja|Yes|Ja|  
|`NetNamedPipeBinding`|Ja|nein|Nein|  
|`NetMsmqBinding`|Ja|Ja|Nein|  
|`MsmqIntegrationBinding`|Ja|Nein|Nein|  
|`wsFederationHttpBinding`|Nein|Ja|Ja|  
  
## Transportieren von Anmeldeinformationen in Bindungen  
 In der folgenden Tabelle werden die Typen von Clientanmeldeinformationen aufgeführt, die bei der Nutzung von `BasicHttpBinding` oder `WSHttpBinding` im Transportsicherheitsmodus zur Verfügung stehen.  
  
|Typ|Beschreibung|  
|---------|------------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss.Dies führt zur Verwendung eines anonymen Clients.|  
|Standard|Standardauthentifizierung.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] RFC 2617, HTTP\-Authentifizierung: Standard\- und Digestauthentifizierung, verfügbar unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=84023](http://go.microsoft.com/fwlink/?LinkId=84023) \(möglicherweise in englischer Sprache\).|  
|Digest|Digestauthentifizierung.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] RFC 2617, HTTP\-Authentifizierung: Standard\- und Digestauthentifizierung, verfügbar unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=84023](http://go.microsoft.com/fwlink/?LinkId=84023) \(möglicherweise in englischer Sprache\).|  
|NTLM|NT\-LAN\-Manager \(NTLM\)\-Authentifizierung.|  
|Windows|Windows\-Authentifizierung.|  
|Zertifikat|Die Authentifizierung fand über ein Zertifikat statt.|  
|IssuedToken|Ermöglicht dem Dienst die Forderung, dass der Client über ein Token, das von einem Sicherheitstokendienst oder von [!INCLUDE[infocard](../../../../includes/infocard-md.md)] ausgestellt wurde, authentifiziert werden muss.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
### Clientanmeldeinformationen für Nachrichten in Bindungen  
 In der folgenden Tabelle werden die Typen von Clientanmeldeinformationen aufgeführt, die bei der Nutzung einer Bindung im Nachrichtensicherheitsmodus zur Verfügung stehen.  
  
|Typ|Beschreibung|  
|---------|------------------|  
|Keine \(None\)|Ermöglicht dem Dienst, mit anonymen Clients zu interagieren.|  
|Windows|Ermöglicht SOAP\-Nachrichtenaustausch im Rahmen des authentifizierten Kontexts von Windows\-Anmeldeinformationen.|  
|UserName|Ermöglicht dem Dienst die Forderung an den Client, sich über eine Benutzernamen\-Anmeldeinformation zu authentifizieren.Bitte beachten Sie, dass bei einer Festlegung des Sicherheitsmodus auf `TransportWithMessageCredential`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] das Senden eines Kennwortdigest oder die Ableitung von Schlüsseln über das Kennwort und die Verwendung solcher Schlüssel für die Nachrichtenmodussicherheit nicht unterstützt werden.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] setzt prinzipiell durch, dass der Transport gesichert wird, wenn er Benutzernamen\-Anmeldeinformationen verwendet.|  
|Zertifikat|Ermöglicht es dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss.|  
|IssuedToken|Ermöglicht es dem Dienst, einen Sicherheitstokendienst zu verwenden, um ein benutzerdefiniertes Token zu liefern.|  
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Wählen eines Typs von Anmeldeinformationen](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)