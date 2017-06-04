---
title: "&#220;bersicht &#252;ber Windows Communication Foundation-Bindungen | Microsoft Docs"
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
  - "Bindungen [WCF], Übersicht"
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &#220;bersicht &#252;ber Windows Communication Foundation-Bindungen
Bindungen sind Objekte, die die zum Herstellen einer Verbindung zum Endpunkt eines [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienstes erforderlichen Kommunikationsdetails angeben.  Jeder Endpunkt in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst erfordert eine korrekt angegebene Bindung.  In diesem Thema werden die Typen von Kommunikationsdetails, die die Bindungen definieren, die Elemente einer Bindung, die in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enthaltenen Bindungen und Methoden zum Angeben einer Bindung für einen Endpunkt aufgeführt.  
  
## Was eine Bindung definiert  
 Die Informationen in einer Bindung können sehr einfach oder sehr komplex sein.  Die einfachste Bindung gibt nur das Transportprotokoll \(wie HTTP\) an, das für die Verbindung zum Endpunkt verwendet werden muss.  Allgemeiner gesagt fallen die Informationen in einer Bindung zur Verbindung mit einem Endpunkt in eine der folgenden Kategorien.  
  
 Protokolle  
 Bestimmt den verwendeten Sicherheitsmechanismus, entweder zuverlässige Messagingfähigkeit oder Transaktionskontextablauf\-Einstellungen.  
  
 Codierung  
 Bestimmt die Nachrichtencodierung \(z. B. Text oder binär\).  
  
 Transport  
 Bestimmt das zu verwendende zugrunde liegende Transportprotokoll \(z. B. TCP oder HTTP\).  
  
## Die Elemente einer Bindung  
 Eine Bindung besteht im Allgemeinen aus einem geordneten Stapel von Bindungselementen, die jeweils einen Teil der für die Verbindung zu einem Dienstendpunkt erforderlichen Kommunikationsinformationen angeben.  Die beiden niedrigsten Ebenen im Stapel sind jeweils erforderlich.  An der Basis des Stapels befindet sich das Transportbindungselement und unmittelbar darüber das Element, das die Spezifikationen für die Nachrichtencodierung enthält.  Die optionalen Bindungselemente, die die anderen Kommunikationsprotokolle angeben, befinden sich in den Ebenen oberhalb dieser beiden erforderlichen Elemente.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu diesen Bindungselementen und ihrer korrekten Anordnung finden Sie unter [Benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## Vom System bereitgestellte Bindungen  
 Die Informationen in einer Bindung können komplex sein, und einige Einstellungen sind möglicherweise mit anderen nicht kompatibel.  Aus diesem Grund schließt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] einen Satz vom System bereitgestellter Bindungen ein.  Diese Bindungen sind für die meisten Anwendungsanforderungen vorgesehen.  Die folgenden Klassen stellen einige Beispiele für vom System bereitgestellte Bindungen dar:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Eine für Verbindungen zu Webdiensten geeignete HTTP\-Protokollbindung, die der WS\-I Basic Profile\-Spezifikation entspricht \(z. B. auf ASP.NET\-Webdiensten basierte Dienste\).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Eine für Verbindungen zu Endpunkten geeignete interoperable Bindung, die den WS\-\*\-Protokollen entspricht.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Verwendet [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zum Herstellen von Verbindungen mit anderen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Endpunkten auf dem gleichen Computer.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Verwendet [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zum Herstellen von Verbindungen für Nachrichten in der Warteschlange mit anderen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Endpunkten.  
  
 Eine vollständige Liste aller von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bereitgestellten Bindungen mit Beschreibungen finden Sie unter [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Verwenden der eigenen Bindungen  
 Wenn keine der vom System bereitgestellten Bindungen über die richtige Kombination von Funktionen verfügt, die für eine Dienstanwendung erforderlich sind, können Sie eine eigene Bindung erstellen.  Hierfür gibt es zwei Möglichkeiten.  Sie können eine neue Bindung entweder mithilfe eines <xref:System.ServiceModel.Channels.CustomBinding>\-Objekts aus bereits vorhandenen Bindungselementen erstellen oder durch Ableiten von der <xref:System.ServiceModel.Channels.Binding>\-Bindung eine vollständig benutzerdefinierte Bindung erstellen.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Erstellen der eigenen Bindung mit diesen beiden Ansätzen finden Sie unter [Benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md) und [Erstellen benutzerdefinierter Bindungen](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## Verwenden von Bindungen  
 Das Verwenden von Bindungen umfasst zwei grundlegende Schritte:  
  
1.  Auswählen oder Definieren einer Bindung.  Die einfachste Methode ist, eine in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enthaltene, vom System bereitgestellte Bindung auszuwählen und sie mit ihren Standardeinstellungen zu verwenden.  Sie können auch eine vom System bereitgestellte Bindung auswählen und ihre Eigenschaftswerte zurücksetzen, um sie Ihren Anforderungen anzupassen.  Alternativ können Sie eine benutzerdefinierte Bindung erstellen, um ein höheres Maß an Steuerung und Anpassung zu erreichen.  
  
2.  Erstellen Sie einen Endpunkt, der die ausgewählte oder definierte Bindung verwendet.  
  
## Code und Konfiguration  
 Sie können Bindungen mit zwei Methoden definieren: durch Code oder durch Konfiguration.  Diese beiden Ansätze hängen nicht davon ab, ob Sie eine vom System bereitgestellte Bindung oder eine benutzerdefinierte Bindung verwenden.  Im Allgemeinen gibt Ihnen die Verwendung von Code die vollständige Kontrolle über die Definition einer Bindung zur Entwurfszeit.  Mit der Konfiguration kann andererseits ein Systemadministrator oder der Benutzer eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstes oder \-Clients die Parameter einer Bindung ändern, ohne die Dienstanwendung neu kompilieren zu müssen.  Diese Flexibilität ist häufig wünschenswert, da die spezifischen Computeranforderungen, für die eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendung bereitgestellt werden soll, nicht vorhersehbar sind.  Das Ausschließen der Bindungsinformationen \(und der Adressierungsinformationen\) aus dem Code ermöglicht deren Änderung, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  Beachten Sie, dass im Code definierte Bindungen nach in der Konfiguration angegebenen Bindungen erstellt werden, sodass die durch den Code definierten Bindungen alle durch die Konfiguration definierten Bindungen überschreiben kann.  
  
## Siehe auch  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)