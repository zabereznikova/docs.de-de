---
title: Konfigurieren der vom System bereitgestellten Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
ms.openlocfilehash: d6018c8339cb04471bf9ce0f2ee86e091e1d1e95
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597526"
---
# <a name="configuring-system-provided-bindings"></a>Konfigurieren der vom System bereitgestellten Bindungen
Bindungen geben den Kommunikationsmechanismus für die Kommunikation mit einem Endpunkt und die zum Herstellen einer Verbindung mit einem Endpunkt erforderlichen Kommunikationsdetails an. Bindungen bestehen aus Elementen, die definieren, wie die Windows Communication Foundation (WCF)-Kanäle angeordnet werden, um die erforderlichen Kommunikations Features bereitzustellen. Eine Bindung enthält drei Arten von Elementen:  
  
- Bindungselemente für den Protokollkanal, die die Einstellungen bezüglich Sicherheit, Zuverlässigkeit und Kontextablauf oder benutzerdefinierte Protokolle festlegen, die beim Senden von Nachrichten zum Endpunkt verwendet werden sollen.  
  
- Bindungselemente für den Transportkanal, die das zugrunde liegende Transportprotokoll festlegen, das zum Senden von Nachrichten zum Endpunkt verwendet werden soll, beispielsweise TCP oder HTTP.  
  
- Bindungselemente für die Nachrichtencodierung, die die Codierung festlegen, z.&#160;B. Text/XML, binär oder MTOM (Message Transmission Optimization Mechanism), die für Nachrichten, die an den Endpunkt gesendet werden, verwendet werden soll.  
  
 In diesem Thema werden alle vom System bereitgestellten Windows Communication Foundation (WCF)-Bindungen dargestellt. Wenn keine dieser Bindungen die Anforderungen der Anwendung erfüllt, können Sie mithilfe der <xref:System.ServiceModel.Channels.CustomBinding>-Klasse eine Bindung erstellen. Weitere Informationen zum Erstellen benutzerdefinierter Bindungen finden Sie unter [Benutzerdefinierte Bindungen](../extending/custom-bindings.md).  
  
> [!IMPORTANT]
> Wählen Sie eine Bindung aus, bei der die Sicherheitsfunktionen aktiviert sind. Standardmäßig weisen alle Bindungen, mit Ausnahme der <xref:System.ServiceModel.BasicHttpBinding>-Bindung, aktivierte Sicherheitsfunktionen auf. Wenn Sie keine sichere Bindung auswählen oder Sicherheitsfunktionen deaktivieren, müssen Sie den Datenaustausch im Netzwerk auf eine andere Weise schützen, z.&#160;B. durch ein geschütztes Datencenter oder ein isoliertes Netzwerk.  
  
> [!IMPORTANT]
> Verwenden Sie nur dann Duplexverträge mit Bindungen, die keine Sicherheitsfunktionen unterstützen oder bei denen die Sicherheitsfunktionen deaktiviert sind, wenn der Datenaustausch im Netzwerk auf andere Weise geschützt wird.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Die folgenden Bindungen werden mit WCF ausgeliefert.  
  
|Bindung|Konfigurationselement|BESCHREIBUNG|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|Eine Bindung, die sich für die Kommunikation mit Webdiensten eignet, die dem WS-Basic Profile entsprechen, beispielsweise auf ASP.NET-Webdiensten (ASMX) basierende Dienste. Diese Bindung verwendet HTTP als Transport und Text/XML als Standardnachrichtencodierung.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die sich für Nicht-Duplexdienstverträge eignet.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<ws2007HttpBinding>](../../configure-apps/file-schema/wcf/ws2007httpbinding.md)|Eine sichere und vollständig kompatible Bindung, die Unterstützung für die entsprechenden Versionen der Bindungselemente <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> und <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> bereitstellt.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die für Duplexdienstverträge oder für die Kommunikation über SOAP-Vermittler geeignet ist.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die das WS-Federationprotokoll unterstützt, und es damit einem Verbund angehörenden Organisationen ermöglicht, Benutzer effizient zu authentifizieren und zu autorisieren.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<ws2007FederationHttpBinding>](../../configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die von <xref:System.ServiceModel.WS2007HttpBinding> abgeleitet ist und Verbundsicherheit unterstützt.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|Eine sichere und optimierte Bindung, die sich für die computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md)|Eine sichere, zuverlässige und optimierte Bindung, die sich für die Kommunikation zwischen WCF-Anwendungen auf einem Computer eignet.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|Eine der Warteschlange hinzugefügte Bindung, die sich für eine computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../../configure-apps/file-schema/wcf/netpeertcpbinding.md)|Eine Bindung, die eine sichere Kommunikation zwischen mehreren Computern ermöglicht.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../configure-apps/file-schema/wcf/webhttpbinding.md)|Eine Bindung, die zum Konfigurieren von Endpunkten für WCF-Webdienste verwendet wird, die durch HTTP-Anforderungen und nicht durch SOAP-Nachrichten bereitgestellt werden.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Eine Bindung, die für die Computer übergreifende Kommunikation zwischen einer WCF-Anwendung und vorhandenen Message Queuing (auch MSMQ)-Anwendungen geeignet ist.|  
  
## <a name="binding-features"></a>Binden von Funktionen  
 In der nächsten Tabelle sind einige der wichtigsten Funktionen der einzelnen vom System bereitgestellten Bindungen dargestellt. Die Bindungen sind in der ersten Tabellenspalte angegeben, und die Informationen zu den Funktionen werden in der Tabelle beschrieben. In der folgenden Tabelle werden die im Zusammenhang mit Bindungen verwendeten Abkürzungen erklärt. Zur Auswahl einer Bindung ermitteln Sie, welche Spalte in den Zeilen alle Funktionen enthält, die Sie benötigen.  
  
|Bindung|Interoperabilität|Sicherheitsmodus (Standard)|Sitzung<br /><br /> (Standardwert)|Transaktionen|Duplex|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Keine), Transport, Nachricht, Gemischt|Keine (Keine)|(Keine)|–|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|(Keine), Transport, (Nachricht), Gemischt|(Keine), Transport, zuverlässige Sitzung|(Keine), Ja|–|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-Security, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|(Keine), Transport, (Nachricht), Gemischt|(Keine), Transport, zuverlässige Sitzung|(Keine), Ja|–|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|Keine, (Nachricht)|(Zuverlässige Sitzung)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|Keine, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|Keine, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|Keine, (Transport), Nachricht<br /><br /> Mixed|Zuverlässige Sitzung, (Transport)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|Keine<br /><br /> (Transport)|Keine, (Transport)|(Keine), Ja|Ja|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Keine, Nachricht, (Transport), Beide|(Keine)|(Keine), Ja|Nein|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|Keine, Nachricht, (Transport), Gemischt|(Keine)|(Keine)|Ja|  
|<xref:System.ServiceModel.WebHttpBinding>|.Net|Keine, Transport, transportkredentialonly|(Keine)|(Keine)|–|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|Keine, (Transport)|(Keine)|(Keine), Ja|–|  
  
 Die in der vorstehenden Tabelle aufgeführten Funktionen werden in der folgenden Tabelle erläutert.  
  
|Funktion|BESCHREIBUNG|  
|-------------|-----------------|  
|Interoperabilitätstyp|Benennt das Protokoll oder die Technologie, mit dem bzw. der in der Bindung die Zusammenarbeit sichergestellt wird.|  
|Sicherheit|Gibt an, wie der Kanal geschützt wird.<br /><br /> -None: die SOAP-Nachricht ist nicht gesichert, und der Client wird nicht authentifiziert.<br />-Transport: die Sicherheitsanforderungen werden auf der Transport Ebene erfüllt.<br />-Message: die Sicherheitsanforderungen werden auf der Nachrichten Ebene erfüllt.<br />-Gemischt: Dieser Sicherheitsmodus wird als bezeichnet `TransportWithMessageCredentials` . Die Anmeldeinformationen werden auf der Nachrichtenebene übermittelt, und die Anforderungen an Integrität und Vertraulichkeit werden auf der Transportebene erfüllt.<br />-Both: sowohl die Nachrichten Ebene als auch die Sicherheit auf Transport Ebene werden verwendet. Über diese Fähigkeit verfügt nur die <xref:System.ServiceModel.NetMsmqBinding>-Bindung.|  
|Sitzung|Gibt an, ob die betreffende Bindung Sitzungsverträge unterstützt.|  
|Transaktionen|Gibt an, ob Transaktionen ermöglicht werden.|  
|Duplex|Gibt an, ob Duplexverträge unterstützt werden. Beachten Sie, dass diese Funktion Bindungsunterstützung für Sitzungen erfordert.|  
|Streaming|Gibt an, ob das Nachrichtenstreaming unterstützt wird.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Endpunkterstellung](../endpoint-creation-overview.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../using-bindings-to-configure-services-and-clients.md)
- [Einfache WCF-Programmierung](../basic-wcf-programming.md)
