---
title: Übersicht über Windows Communication Foundation-Bindungen
description: Erfahren Sie mehr über Bindungen, die angeben, wie eine Verbindung mit einem WCF-Dienst hergestellt wird, einschließlich der Elemente einer Bindung und der Angabe einer Bindung für einen Dienst Endpunkt.
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
ms.openlocfilehash: da8050c4e9aeb111de3a54315b3650bcf09f23ed
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247713"
---
# <a name="windows-communication-foundation-bindings-overview"></a>Übersicht über Windows Communication Foundation-Bindungen
Bindungen sind Objekte, mit denen die Kommunikations Details angegeben werden, die erforderlich sind, um eine Verbindung mit dem Endpunkt eines Windows Communication Foundation (WCF)-Dienstanbieter herzustellen. Jeder Endpunkt in einem WCF-Dienst erfordert eine wohldefinierte Bindung. In diesem Thema werden die Arten von Kommunikations Details erläutert, die von den Bindungen definiert werden, die Elemente einer Bindung, welche Bindungen in WCF enthalten sind und wie eine Bindung für einen Endpunkt angegeben werden kann.  
  
## <a name="what-a-binding-defines"></a>Was eine Bindung definiert  
 Die Informationen in einer Bindung können sehr einfach oder sehr komplex sein. Die einfachste Bindung gibt nur das Transportprotokoll (wie HTTP) an, das für die Verbindung zum Endpunkt verwendet werden muss. Im allgemeinen fallen die Informationen, die eine Bindung zum Herstellen einer Verbindung mit einem Endpunkt enthält, in eine der folgenden Kategorien:  
  
 **Protokolle**  
 Bestimmt den verwendeten Sicherheitsmechanismus, entweder zuverlässige Messagingfähigkeit oder Transaktionskontextablauf-Einstellungen.  
  
 **Codieren**  
 Bestimmt die Nachrichtencodierung (z. B. Text oder binär).  
  
 **Transport**  
 Bestimmt das zu verwendende zugrunde liegende Transportprotokoll (z. B. TCP oder HTTP).  
  
## <a name="the-elements-of-a-binding"></a>Die Elemente einer Bindung  
 Eine Bindung besteht im Allgemeinen aus einem geordneten Stapel von Bindungselementen, die jeweils einen Teil der für die Verbindung zu einem Dienstendpunkt erforderlichen Kommunikationsinformationen angeben. Die beiden niedrigsten Ebenen im Stapel sind jeweils erforderlich. An der Basis des Stapels befindet sich das Transportbindungselement und unmittelbar darüber das Element, das die Spezifikationen für die Nachrichtencodierung enthält. Die optionalen Bindungselemente, die die anderen Kommunikationsprotokolle angeben, befinden sich in den Ebenen oberhalb dieser beiden erforderlichen Elemente. Weitere Informationen zu diesen Bindungs Elementen und ihrer korrekten Reihenfolge finden Sie unter [benutzerdefinierte Bindungen](./extending/custom-bindings.md).  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Die Informationen in einer Bindung können komplex sein, und einige Einstellungen sind möglicherweise mit anderen nicht kompatibel. Aus diesem Grund enthält WCF eine Reihe von vom System bereitgestellten Bindungen. Diese Bindungen sind für die meisten Anwendungsanforderungen vorgesehen. Die folgenden Klassen stellen einige Beispiele für vom System bereitgestellte Bindungen dar:  
  
- <xref:System.ServiceModel.BasicHttpBinding>: Eine für Verbindungen zu Webdiensten geeignete HTTP-Protokollbindung, die der WS-I Basic Profile-Spezifikation entspricht (z. B. auf ASP.NET-Webdiensten basierte Dienste).  
  
- <xref:System.ServiceModel.WSHttpBinding>: Eine für Verbindungen zu Endpunkten geeignete interoperable Bindung, die den WS-*-Protokollen entspricht.  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>: Verwendet die .NET Framework, um eine Verbindung mit anderen WCF-Endpunkten auf dem gleichen Computer herzustellen.  
  
- <xref:System.ServiceModel.NetMsmqBinding>: Verwendet die .NET Framework, um Nachrichten Verbindungen in der Warteschlange mit anderen WCF-Endpunkten zu erstellen.  

- <xref:System.ServiceModel.NetTcpBinding>: Diese Bindung bietet eine höhere Leistung als HTTP-Bindungen und eignet sich ideal für die Verwendung in einem lokalen Netzwerk.
  
 Eine vollständige Liste mit Beschreibungen aller von WCF bereitgestellten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md).  
  
## <a name="using-your-own-bindings"></a>Verwenden der eigenen Bindungen  
 Wenn keine der vom System bereitgestellten Bindungen über die richtige Kombination von Funktionen verfügt, die für eine Dienstanwendung erforderlich sind, können Sie eine eigene Bindung erstellen. Es gibt hierbei zwei Möglichkeiten. Sie können eine neue Bindung entweder mithilfe eines <xref:System.ServiceModel.Channels.CustomBinding>-Objekts aus bereits vorhandenen Bindungselementen erstellen oder durch Ableiten von der <xref:System.ServiceModel.Channels.Binding>-Bindung eine vollständig benutzerdefinierte Bindung erstellen. Weitere Informationen zum Erstellen einer eigenen Bindung mit diesen beiden Ansätzen finden Sie unter [benutzerdefinierte Bindungen](./extending/custom-bindings.md) und [Erstellen benutzerdefinierter Bindungen](./extending/creating-user-defined-bindings.md).  
  
## <a name="using-bindings"></a>Verwenden von Bindungen  
 Das Verwenden von Bindungen umfasst zwei grundlegende Schritte:  
  
1. Auswählen oder Definieren einer Bindung. Die einfachste Methode besteht darin, eine der vom System bereitgestellten Bindungen in WCF auszuwählen und diese mit ihren Standardeinstellungen zu verwenden. Sie können auch eine vom System bereitgestellte Bindung auswählen und ihre Eigenschaftswerte zurücksetzen, um sie Ihren Anforderungen anzupassen. Alternativ können Sie eine benutzerdefinierte Bindung erstellen, um ein höheres Maß an Steuerung und Anpassung zu erreichen.  
  
2. Erstellen Sie einen Endpunkt, der die ausgewählte oder definierte Bindung verwendet.  
  
## <a name="code-and-configuration"></a>Code und Konfiguration  
 Sie können Bindungen mit zwei Methoden definieren: durch Code oder durch Konfiguration. Diese beiden Ansätze hängen nicht davon ab, ob Sie eine vom System bereitgestellte Bindung oder eine benutzerdefinierte Bindung verwenden. Im Allgemeinen gibt Ihnen die Verwendung von Code die vollständige Kontrolle über die Definition einer Bindung zur Entwurfszeit. Mithilfe der Konfiguration hingegen kann ein Systemadministrator oder der Benutzer eines WCF-Dienstanbieters oder-Clients die Parameter einer Bindung ändern, ohne dass die Dienst Anwendung neu kompiliert werden muss. Diese Flexibilität ist häufig wünschenswert, da es keine Möglichkeit gibt, bestimmte Computeranforderungen vorherzusagen, auf denen eine WCF-Anwendung bereitgestellt werden soll. Das Ausschließen der Bindungsinformationen (und der Adressierungsinformationen) aus dem Code ermöglicht deren Änderung, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen. Beachten Sie, dass im Code definierte Bindungen nach in der Konfiguration angegebenen Bindungen erstellt werden, sodass die durch den Code definierten Bindungen alle durch die Konfiguration definierten Bindungen überschreiben können.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
