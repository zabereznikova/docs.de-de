---
title: Übersicht über Windows Communication Foundation-Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
ms.openlocfilehash: 90da8f4a2b4efeb684cbe9e5513084e6d1c6f515
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325058"
---
# <a name="windows-communication-foundation-bindings-overview"></a>Übersicht über Windows Communication Foundation-Bindungen
Bindungen sind Objekte, mit denen die Kommunikationsdetails angeben, die eine Verbindung mit dem Endpunkt eines Windows Communication Foundation (WCF)-Diensts erforderlich sind. Jeder Endpunkt in einem WCF-Dienst erfordert eine wohldefinierte Bindung. Dieses Thema beschreibt die Typen von Kommunikationsdetails, die die Bindungen definieren die Elemente einer Bindung, welche Bindungen in WCF enthalten sind und wie eine Bindung für einen Endpunkt angegeben werden kann.  
  
## <a name="what-a-binding-defines"></a>Was eine Bindung definiert  
 Die Informationen in einer Bindung können sehr einfach oder sehr komplex sein. Die einfachste Bindung gibt nur das Transportprotokoll (wie HTTP) an, das für die Verbindung zum Endpunkt verwendet werden muss. Allgemeiner gesagt fallen die Informationen in einer Bindung zur Verbindung mit einem Endpunkt in eine der folgenden Kategorien.  
  
 Protokolle  
 Bestimmt den verwendeten Sicherheitsmechanismus, entweder zuverlässige Messagingfähigkeit oder Transaktionskontextablauf-Einstellungen.  
  
 Codierung  
 Bestimmt die Nachrichtencodierung (z. B. Text oder binär).  
  
 Transport  
 Bestimmt das zu verwendende zugrunde liegende Transportprotokoll (z. B. TCP oder HTTP).  
  
## <a name="the-elements-of-a-binding"></a>Die Elemente einer Bindung  
 Eine Bindung besteht im Allgemeinen aus einem geordneten Stapel von Bindungselementen, die jeweils einen Teil der für die Verbindung zu einem Dienstendpunkt erforderlichen Kommunikationsinformationen angeben. Die beiden niedrigsten Ebenen im Stapel sind jeweils erforderlich. An der Basis des Stapels befindet sich das Transportbindungselement und unmittelbar darüber das Element, das die Spezifikationen für die Nachrichtencodierung enthält. Die optionalen Bindungselemente, die die anderen Kommunikationsprotokolle angeben, befinden sich in den Ebenen oberhalb dieser beiden erforderlichen Elemente. Weitere Informationen zu diesen Bindungselementen und ihrer korrekten Anordnung finden Sie unter [benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Die Informationen in einer Bindung können komplex sein, und einige Einstellungen sind möglicherweise mit anderen nicht kompatibel. Aus diesem Grund enthält WCF eine Reihe von vom System bereitgestellten Bindungen. Diese Bindungen sind für die meisten Anwendungsanforderungen vorgesehen. Die folgenden Klassen stellen einige Beispiele für vom System bereitgestellte Bindungen dar:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Ein HTTP-Protokoll für Verbindungen zu Webdiensten geeignete Bindung, die konform, die der WS-I Basic Profile-Spezifikation (z. B. ASP.NET Web Services-basierte Dienste).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Eine interoperable Bindung, die für Verbindungen mit Endpunkten, die die WS - entsprechen, geeignete * Protokolle.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Verwendet die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zur Verbindung mit anderen WCF-Endpunkten auf demselben Computer.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Verwendet die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Nachrichten in der Warteschlange Verbindungen mit anderen WCF-Endpunkten zu erstellen.  

- <xref:System.ServiceModel.NetTcpBinding>: Diese Bindung bietet eine höhere Leistung als HTTP-Bindungen und eignet sich ideal für die Verwendung in einem lokalen Netzwerk.
  
 Eine vollständige Liste mit Beschreibungen der alle WCF-Bindungen, finden Sie unter [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="using-your-own-bindings"></a>Verwenden der eigenen Bindungen  
 Wenn keine der vom System bereitgestellten Bindungen über die richtige Kombination von Funktionen verfügt, die für eine Dienstanwendung erforderlich sind, können Sie eine eigene Bindung erstellen. Hierfür gibt es zwei Möglichkeiten. Sie können eine neue Bindung entweder mithilfe eines <xref:System.ServiceModel.Channels.CustomBinding>-Objekts aus bereits vorhandenen Bindungselementen erstellen oder durch Ableiten von der <xref:System.ServiceModel.Channels.Binding>-Bindung eine vollständig benutzerdefinierte Bindung erstellen. Weitere Informationen zum Erstellen der eigenen Bindung mit diesen beiden Ansätzen finden Sie unter [benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md) und [Erstellen benutzerdefinierter Bindungen](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="using-bindings"></a>Verwenden von Bindungen  
 Das Verwenden von Bindungen umfasst zwei grundlegende Schritte:  
  
1. Auswählen oder Definieren einer Bindung. Die einfachste Methode ist, wählen Sie eine der vom System bereitgestellten Bindungen, die in WCF enthalten, und es mit den Standardeinstellungen zu verwenden. Sie können auch eine vom System bereitgestellte Bindung auswählen und ihre Eigenschaftswerte zurücksetzen, um sie Ihren Anforderungen anzupassen. Alternativ können Sie eine benutzerdefinierte Bindung erstellen, um ein höheres Maß an Steuerung und Anpassung zu erreichen.  
  
2. Erstellen Sie einen Endpunkt, der die ausgewählte oder definierte Bindung verwendet.  
  
## <a name="code-and-configuration"></a>Code und Konfiguration  
 Sie können Bindungen mit zwei Methoden definieren: durch Code oder durch Konfiguration. Diese beiden Ansätze hängen nicht davon ab, ob Sie eine vom System bereitgestellte Bindung oder eine benutzerdefinierte Bindung verwenden. Im Allgemeinen gibt Ihnen die Verwendung von Code die vollständige Kontrolle über die Definition einer Bindung zur Entwurfszeit. Mit der Konfiguration ermöglicht andererseits, ein Systemadministrator oder der Benutzer einen WCF-Dienst oder Client, der Parameter einer Bindung zu ändern, ohne die dienstanwendung neu kompilieren. Diese Flexibilität ist häufig wünschenswert, da es keine Möglichkeit zur Vorhersage, für die spezifischen computeranforderungen eine WCF-Anwendung bereitgestellt werden. Das Ausschließen der Bindungsinformationen (und der Adressierungsinformationen) aus dem Code ermöglicht deren Änderung, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen. Beachten Sie, dass im Code definierte Bindungen nach in der Konfiguration angegebenen Bindungen erstellt werden, sodass die durch den Code definierten Bindungen alle durch die Konfiguration definierten Bindungen überschreiben können.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
