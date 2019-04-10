---
title: Verwenden von Bindungen, um Dienste und Clients zu konfigurieren
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
ms.openlocfilehash: 3b4f00617418d5f84a0da5d0e531e1f671b58bb1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323147"
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Verwenden von Bindungen, um Dienste und Clients zu konfigurieren
Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails angeben. Genauer gesagt enthalten Bindungen Konfigurationsinformationen, die zum Erstellen der Client- oder Dienstlaufzeit durch Festlegen der Merkmale von Transporten, Übertragungsformaten (Nachrichtencodierung) und Protokollen für den entsprechenden Endpunkt oder Clientkanal verwendet werden. Um einen funktionierenden Windows Communication Foundation (WCF)-Dienst zu erstellen, erfordert jeder Endpunkt im Dienst eine Bindung an. In diesem Thema wird erläutert, was Bindungen sind, wie sie definiert werden und wie eine bestimmte Bindung für einen Endpunkt angegeben wird.  
  
## <a name="what-a-binding-defines"></a>Was eine Bindung definiert  
 Die Informationen in einer Bindung können sehr einfach oder sehr komplex sein. Die einfachste Bindung gibt nur das Transportprotokoll (wie HTTP) an, das für die Verbindung zum Endpunkt verwendet werden muss. Allgemeiner gesagt fallen die Informationen in einer Bindung zur Verbindung mit einem Endpunkt in eine der Kategorien in der folgenden Tabelle.  
  
 Protokolle  
 Bestimmt den verwendeten Sicherheitsmechanismus, entweder zuverlässige Messagingfähigkeit oder Transaktionskontextablauf-Einstellungen.  
  
 Transport  
 Bestimmt das zu verwendende zugrunde liegende Transportprotokoll (z. B. TCP oder HTTP).  
  
 Codierung  
 Bestimmt die Nachrichtencodierung, z. B. Text/XML, binär oder MTOM (Message Transmission Optimization Mechanism), die festlegt, wie Nachrichten bei Übertragungen als Bytestreams dargestellt werden.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 WCF umfasst eine Reihe von vom System bereitgestellten Bindungen, mit denen meisten anwendungsanforderungen und Szenarien abdecken. Die folgenden Klassen stellen einige Beispiele für vom System bereitgestellte Bindungen dar:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Ein HTTP-Protokoll für Verbindungen zu Webdiensten geeignete Bindung, die konform, die der WS-I Basic Profile 1.1-Spezifikation (z. B. ASP.NET-Webdienste [ASMX]-basierte Dienste).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Eine HTTP-protokollbindung geeignet für die Verbindung mit Endpunkten, die im Internet entsprechen, services webdienstespezifikations-Protokollen.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Die binäre .NET-Codierung und rahmentechnologien zusammen mit der Windows named Pipe-Transport verwendet für die Verbindung mit anderen WCF-Endpunkten auf demselben Computer.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Verwendet die binäre .NET-Codierung und rahmentechnologien zusammen mit der Message Queuing (auch bekannt als MSMQ) zum Erstellen von Nachrichten in der Warteschlange Verbindungen mit anderen WCF-Endpunkten.  
  
 Eine vollständige Liste der vom System bereitgestellten Bindungen mit Beschreibungen finden Sie unter [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen  
 Wenn die Auflistung vom System bereitgestellter Bindungen nicht die richtige Kombination von Funktionen aufweist, die für eine Dienstanwendung erforderlich ist, können Sie eine <xref:System.ServiceModel.Channels.CustomBinding>-Bindung erstellen. Weitere Informationen zu den Elementen von einem <xref:System.ServiceModel.Channels.CustomBinding> Bindung, finden Sie unter [ \<CustomBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) und [benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Verwenden von Bindungen  
 Das Verwenden von Bindungen umfasst zwei grundlegende Schritte:  
  
1. Auswählen oder Definieren einer Bindung. Die einfachste Methode ist, eine vom System bereitgestellte Bindung auszuwählen und ihre Standardeinstellungen zu verwenden. Sie können auch eine vom System bereitgestellte Bindung auswählen und ihre Eigenschaftswerte zurücksetzen, um sie Ihren Anforderungen anzupassen. Alternativ können Sie eine benutzerdefinierte Bindung erstellen und jede Eigenschaft nach Bedarf festlegen.  
  
2. Erstellen eines Endpunkts, der diese Bindung verwendet.  
  
## <a name="code-and-configuration"></a>Code und Konfiguration  
 Sie können Bindungen durch Code bzw. Konfiguration definieren oder konfigurieren. Diese beiden Ansätze sind unabhängig vom verwendeten Bindungstyp, z. B. ob Sie eine vom System bereitgestellte Bindung oder eine <xref:System.ServiceModel.Channels.CustomBinding>-Bindung verwenden. Im Allgemeinen gibt Ihnen die Verwendung von Code die vollständige Kontrolle über die Definition einer Bindung beim Kompilieren. Mit der Konfiguration ermöglicht andererseits, ein Systemadministrator oder der Benutzer eines WCF-Diensts oder Clients so ändern Sie die Parameter von Bindungen. Diese Flexibilität ist häufig wünschenswert, da es gibt keine Möglichkeit, um vorherzusagen, die spezifischen computeranforderungen und netzwerkbedingungen, die in die ist eine WCF-Anwendung bereitgestellt werden. Durch die Trennung der Bindungsinformationen (und Addressierungsinformationen) vom Code können Administratoren die Bindungsdetails ändern, ohne dass die Anwendung neu kompiliert oder bereitgestellt werden muss. Falls die Bindung im Code definiert ist, überschreibt sie alle in der Konfigurationsdatei vorgenommenen konfigurationsbasierten Definitionen. Beispiele für diese Ansätze finden Sie in den folgenden Themen:  
  
-   [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) enthält ein Beispiel zum Erstellen einer Bindung im Code.  
  
-   [Tutorial: Erstellen eines Windows Communication Foundation-Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md) enthält ein Beispiel zum Erstellen eines Clients mit der Konfiguration.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Angeben einer Dienstbindung im Code](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
- [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
- [Vorgehensweise: Angeben einer Clientbindung im Code](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
