---
title: Konfigurieren der vom System bereitgestellten Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
ms.openlocfilehash: 0dc213c2d25558dc447b49d2b2378f9aa72f80a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857414"
---
# <a name="configuring-system-provided-bindings"></a>Konfigurieren der vom System bereitgestellten Bindungen
Bindungen geben den Kommunikationsmechanismus für die Kommunikation mit einem Endpunkt und die zum Herstellen einer Verbindung mit einem Endpunkt erforderlichen Kommunikationsdetails an. Bindungen bestehen aus Elementen, die definieren, wie die Windows Communication Foundation (WCF)-Kanäle Sie Ebenen auf, die erforderlichen Kommunikationsfunktionen bereitzustellen. Eine Bindung enthält drei Arten von Elementen:  
  
- Bindungselemente für den Protokollkanal, die die Einstellungen bezüglich Sicherheit, Zuverlässigkeit und Kontextablauf oder benutzerdefinierte Protokolle festlegen, die beim Senden von Nachrichten zum Endpunkt verwendet werden sollen.  
  
- Bindungselemente für den Transportkanal, die das zugrunde liegende Transportprotokoll festlegen, das zum Senden von Nachrichten zum Endpunkt verwendet werden soll, beispielsweise TCP oder HTTP.  
  
- Bindungselemente für die Nachrichtencodierung, die die Codierung festlegen, z.&amp;#160;B. Text/XML, binär oder MTOM (Message Transmission Optimization Mechanism), die für Nachrichten, die an den Endpunkt gesendet werden, verwendet werden soll.  
  
 Dieses Thema enthält alle vom System bereitgestellten Bindungen für eine Windows Communication Foundation (WCF). Wenn keine dieser Bindungen die Anforderungen der Anwendung erfüllt, können Sie mithilfe der <xref:System.ServiceModel.Channels.CustomBinding>-Klasse eine Bindung erstellen. Weitere Informationen zum Erstellen benutzerdefinierter Bindungen finden Sie unter [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
> [!IMPORTANT]
>  Wählen Sie eine Bindung aus, bei der die Sicherheitsfunktionen aktiviert sind. Standardmäßig weisen alle Bindungen, mit Ausnahme der <xref:System.ServiceModel.BasicHttpBinding>-Bindung, aktivierte Sicherheitsfunktionen auf. Wenn Sie keine sichere Bindung auswählen oder Sicherheitsfunktionen deaktivieren, müssen Sie den Datenaustausch im Netzwerk auf eine andere Weise schützen, z.&amp;#160;B. durch ein geschütztes Datencenter oder ein isoliertes Netzwerk.  
  
> [!IMPORTANT]
>  Verwenden Sie nur dann Duplexverträge mit Bindungen, die keine Sicherheitsfunktionen unterstützen oder bei denen die Sicherheitsfunktionen deaktiviert sind, wenn der Datenaustausch im Netzwerk auf andere Weise geschützt wird.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Die folgenden Bindungen sind mit WCF ausgeliefert.  
  
|Bindung|Konfigurationselement|Beschreibung|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Eine Bindung, die sich für die Kommunikation mit Webdiensten eignet, die dem WS-Basic Profile entsprechen, beispielsweise auf ASP.NET-Webdiensten (ASMX) basierende Dienste. Diese Bindung verwendet HTTP als Transport und Text/XML als Standardnachrichtencodierung.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die sich für Nicht-Duplexdienstverträge eignet.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<ws2007HttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Eine sichere und vollständig kompatible Bindung, die Unterstützung für die entsprechenden Versionen der Bindungselemente <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> und <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> bereitstellt.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die für Duplexdienstverträge oder für die Kommunikation über SOAP-Vermittler geeignet ist.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die das WS-Federationprotokoll unterstützt, und es damit einem Verbund angehörenden Organisationen ermöglicht, Benutzer effizient zu authentifizieren und zu autorisieren.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<ws2007FederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die von <xref:System.ServiceModel.WS2007HttpBinding> abgeleitet ist und Verbundsicherheit unterstützt.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Eine sichere und optimierte Bindung, die sich für die computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Eine sichere, zuverlässige und optimierte Bindung, die sich für die Kommunikation zwischen WCF-Anwendungen auf einem Computer eignet.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Eine der Warteschlange hinzugefügte Bindung, die sich für eine computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Eine Bindung, die eine sichere Kommunikation zwischen mehreren Computern ermöglicht.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Eine Bindung, die zum Konfigurieren von Endpunkten für WCF-Webdienste verwendet wird, die durch HTTP-Anforderungen und nicht durch SOAP-Nachrichten bereitgestellt werden.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Eine Bindung, eignet sich für die computerübergreifende Kommunikation zwischen einem WCF-Anwendung und vorhandenen Message Queuing (auch bekannt als MSMQ) Anwendungen.|  
  
## <a name="binding-features"></a>Binden von Funktionen  
 In der nächsten Tabelle sind einige der wichtigsten Funktionen der einzelnen vom System bereitgestellten Bindungen dargestellt. Die Bindungen sind in der ersten Tabellenspalte angegeben, und die Informationen zu den Funktionen werden in der Tabelle beschrieben. In der folgenden Tabelle werden die im Zusammenhang mit Bindungen verwendeten Abkürzungen erklärt. Zur Auswahl einer Bindung ermitteln Sie, welche Spalte in den Zeilen alle Funktionen enthält, die Sie benötigen.  
  
|Bindung|Interoperabilität|Sicherheitsmodus (Standard)|Sitzung<br /><br /> (Standard)|Transaktionen|Duplex|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Keine), Transport, Nachricht, Gemischt|Keine (Keine)|(Keine)|n/v|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|(Keine), Transport, (Nachricht), Gemischt|(Keine), Transport, zuverlässige Sitzung|(Keine), Ja|n/v|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-Security, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|(Keine), Transport, (Nachricht), Gemischt|(Keine), Transport, zuverlässige Sitzung|(Keine), Ja|n/v|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|Keine, (Nachricht)|(Zuverlässige Sitzung)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|Keine, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|Keine, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|Keine, (Transport), Nachricht<br /><br /> Gemischt|Zuverlässige Sitzung, (Transport)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|Keine<br /><br /> (Transport)|Keine, (Transport)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Keine, Nachricht, (Transport), Beide|(Keine)|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|Keine, Nachricht, (Transport), Gemischt|(Keine)|(Keine)|Ja|  
|<xref:System.ServiceModel.WebHttpBinding>|.Net|None, Transport, TransportCredentialOnly|(Keine)|(Keine)|n/v|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|Keine, (Transport)|(Keine)|(Keine), Ja|n/v|  
  
 Die in der vorstehenden Tabelle aufgeführten Funktionen werden in der folgenden Tabelle erläutert.  
  
|Feature|Beschreibung|  
|-------------|-----------------|  
|Interoperabilitätstyp|Benennt das Protokoll oder die Technologie, mit dem bzw. der in der Bindung die Zusammenarbeit sichergestellt wird.|  
|Sicherheit|Gibt an, wie der Kanal geschützt wird.<br /><br /> – None: Die SOAP-Nachricht nicht gesichert, und der Client ist nicht authentifiziert.<br />-Transport: Sicherheitsanforderungen werden auf der Transportebene erfüllt.<br />-Meldung: Sicherheitsanforderungen werden auf der Nachrichtenebene erfüllt.<br />-Gemischt: Wurde dieser Sicherheitsmodus wird als bezeichnet `TransportWithMessageCredentials`. Die Anmeldeinformationen werden auf der Nachrichtenebene übermittelt, und die Anforderungen an Integrität und Vertraulichkeit werden auf der Transportebene erfüllt.<br />– Beides: Es werden sowohl und auf Transportebene Sicherheit auf Nachrichtenebene verwendet. Über diese Fähigkeit verfügt nur die <xref:System.ServiceModel.NetMsmqBinding>-Bindung.|  
|Sitzung|Gibt an, ob die betreffende Bindung Sitzungsverträge unterstützt.|  
|Transaktionen|Gibt an, ob Transaktionen ermöglicht werden.|  
|Duplex|Gibt an, ob Duplexverträge unterstützt werden. Beachten Sie, dass diese Funktion Bindungsunterstützung für Sitzungen erfordert.|  
|Streaming|Gibt an, ob das Nachrichtenstreaming unterstützt wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Endpunkterstellung](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Einfache WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md)
