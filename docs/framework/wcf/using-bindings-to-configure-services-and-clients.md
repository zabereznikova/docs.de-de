---
title: Verwenden von Bindungen, um Dienste und Clients zu konfigurieren
description: Bindungen enthalten Konfigurationsinformationen, die von WFC-Clients oder-Diensten verwendet werden. Erfahren Sie, wie Sie Bindungen definieren und eine Bindung für einen Dienst Endpunkt angeben.
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
ms.openlocfilehash: 38fa4a928c74f9fff7b67f2479f9304331361fef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289879"
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Verwenden von Bindungen, um Dienste und Clients zu konfigurieren

Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails angeben. Genauer gesagt enthalten Bindungen Konfigurationsinformationen, die zum Erstellen der Client- oder Dienstlaufzeit durch Festlegen der Merkmale von Transporten, Übertragungsformaten (Nachrichtencodierung) und Protokollen für den entsprechenden Endpunkt oder Clientkanal verwendet werden. Um einen funktionierenden Windows Communication Foundation (WCF)-Dienst zu erstellen, ist für jeden Endpunkt im Dienst eine Bindung erforderlich. In diesem Thema wird erläutert, was Bindungen sind, wie sie definiert werden und wie eine bestimmte Bindung für einen Endpunkt angegeben wird.  
  
## <a name="what-a-binding-defines"></a>Was eine Bindung definiert  

 Die Informationen in einer Bindung können sehr einfach oder sehr komplex sein. Die einfachste Bindung gibt nur das Transportprotokoll (wie HTTP) an, das für die Verbindung zum Endpunkt verwendet werden muss. Allgemeiner gesagt fallen die Informationen in einer Bindung zur Verbindung mit einem Endpunkt in eine der Kategorien in der folgenden Tabelle.  
  
 Protokolle  
 Bestimmt den verwendeten Sicherheitsmechanismus, entweder zuverlässige Messagingfähigkeit oder Transaktionskontextablauf-Einstellungen.  
  
 Transport  
 Bestimmt das zu verwendende zugrunde liegende Transportprotokoll (z. B. TCP oder HTTP).  
  
 Codierung  
 Bestimmt die Nachrichtencodierung, z. B. Text/XML, binär oder MTOM (Message Transmission Optimization Mechanism), die festlegt, wie Nachrichten bei Übertragungen als Bytestreams dargestellt werden.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  

 WCF umfasst eine Reihe von vom System bereitgestellten Bindungen, die so konzipiert sind, dass Sie die meisten Anwendungsanforderungen und-Szenarien abdecken. Die folgenden Klassen stellen einige Beispiele für vom System bereitgestellte Bindungen dar:  
  
- <xref:System.ServiceModel.BasicHttpBinding>: Eine für Verbindungen zu Webdiensten geeignete HTTP-Protokollbindung, die der WS-I Basic Profile 1.1-Spezifikation entspricht (z. B. ASP.NET-Webdienste [ASMX]-basierte Dienste).  
  
- <xref:System.ServiceModel.WSHttpBinding>: Eine für Verbindungen zu Endpunkten geeignete HTTP-Protokollbindung, die den Webdienstespezifikations-Protokollen entspricht.  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>: Verwendet die binäre .NET-Codierung und Rahmen Technologien zusammen mit dem Windows Named Pipe-Transport, um eine Verbindung mit anderen WCF-Endpunkten auf dem gleichen Computer herzustellen.  
  
- <xref:System.ServiceModel.NetMsmqBinding>: Verwendet die binäre .net-Codierungs-und-Rahmen Technologien zusammen mit dem Message Queuing (auch als MSMQ bezeichnet), um Nachrichten Verbindungen in der Warteschlange mit anderen WCF-Endpunkten zu erstellen.  
  
 Eine umfassende Liste der vom System bereitgestellten Bindungen mit Beschreibungen finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen  

 Wenn die Auflistung vom System bereitgestellter Bindungen nicht die richtige Kombination von Funktionen aufweist, die für eine Dienstanwendung erforderlich ist, können Sie eine <xref:System.ServiceModel.Channels.CustomBinding>-Bindung erstellen. Weitere Informationen zu den Elementen einer <xref:System.ServiceModel.Channels.CustomBinding> Bindung finden Sie unter [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) und [benutzerdefinierte Bindungen](./extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Verwenden von Bindungen  

 Das Verwenden von Bindungen umfasst zwei grundlegende Schritte:  
  
1. Auswählen oder Definieren einer Bindung. Die einfachste Methode ist, eine vom System bereitgestellte Bindung auszuwählen und ihre Standardeinstellungen zu verwenden. Sie können auch eine vom System bereitgestellte Bindung auswählen und ihre Eigenschaftswerte zurücksetzen, um sie Ihren Anforderungen anzupassen. Alternativ können Sie eine benutzerdefinierte Bindung erstellen und jede Eigenschaft nach Bedarf festlegen.  
  
2. Erstellen eines Endpunkts, der diese Bindung verwendet.  
  
## <a name="code-and-configuration"></a>Code und Konfiguration  

 Sie können Bindungen durch Code bzw. Konfiguration definieren oder konfigurieren. Diese beiden Ansätze sind unabhängig vom verwendeten Bindungstyp, z. B. ob Sie eine vom System bereitgestellte Bindung oder eine <xref:System.ServiceModel.Channels.CustomBinding>-Bindung verwenden. Im Allgemeinen gibt Ihnen die Verwendung von Code die vollständige Kontrolle über die Definition einer Bindung beim Kompilieren. Mithilfe der Konfiguration hingegen kann ein Systemadministrator oder der Benutzer eines WCF-Dienstanbieters oder-Clients die Parameter von Bindungen ändern. Diese Flexibilität ist häufig wünschenswert, da es keine Möglichkeit gibt, die spezifischen Computeranforderungen und Netzwerkbedingungen vorherzusagen, in denen eine WCF-Anwendung bereitgestellt werden soll. Durch die Trennung der Bindungsinformationen (und Addressierungsinformationen) vom Code können Administratoren die Bindungsdetails ändern, ohne dass die Anwendung neu kompiliert oder bereitgestellt werden muss. Falls die Bindung im Code definiert ist, überschreibt sie alle in der Konfigurationsdatei vorgenommenen konfigurationsbasierten Definitionen. Beispiele für diese Ansätze finden Sie in den folgenden Themen:  
  
- Vorgehensweise [: Hosten eines WCF-Diensts in einer verwalteten Anwendung](how-to-host-a-wcf-service-in-a-managed-application.md) bietet ein Beispiel für das Erstellen einer Bindung in Code.  
  
- [Tutorial: Erstellen eines Windows Communication Foundation Clients](how-to-create-a-wcf-client.md) bietet ein Beispiel für das Erstellen eines Clients mithilfe der-Konfiguration.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Endpunkterstellung](endpoint-creation-overview.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Angeben einer Dienstbindung im Code](how-to-specify-a-service-binding-in-code.md)
- [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](how-to-specify-a-client-binding-in-configuration.md)
- [Vorgehensweise: Angeben einer Clientbindung im Code](how-to-specify-a-client-binding-in-code.md)
