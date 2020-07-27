---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter
description: Hier finden Sie eine Übersicht über Benutzeroberflächenautomatisierungs-Anbieter, mit denen Steuerelemente mit Benutzeroberflächenautomatisierungs-Client Anwendungen Überprüfen Sie die Anbieter Typen und die Anbieter Konzepte.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 08b6a199a98fb22f197ca0cf8a0268e5439aaf41
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163242"
---
# <a name="ui-automation-providers-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Benutzeroberflächenautomatisierungs-Anbieter ermöglichen Steuerelementen die Kommunikation mit Clientanwendungen für die Automatisierung der Benutzeroberfläche. Im Allgemeinen wird jedes Steuerelement oder anderes eindeutiges Element auf einer [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] von einem Anbieter dargestellt. Der Anbieter macht Informationen zum Element verfügbar und implementiert optional Steuerelementmuster, die es der Clientanwendung ermöglichen, mit dem Steuerelement zu interagieren.  
  
 Clientanwendungen müssen normalerweise nicht direkt mit Anbietern arbeiten. Die meisten Standard Steuerelemente in Anwendungen, die Win32, Windows Forms oder [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Frameworks verwenden, werden automatisch für das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] System verfügbar gemacht. Anwendungen, die benutzerdefinierte Steuerelemente implementieren, können auch [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter für diese Steuerelemente implementieren, und die Clientanwendungen müssen keine besonderen Schritte ausführen, um Zugriff auf diese zu erlangen.  
  
 Dieses Thema bietet einen Überblick darüber, wie Steuerelement Entwickler [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter implementieren, insbesondere für Steuerelemente in Windows Forms und Win32-Fenstern.  
  
<a name="Types_of_Providers"></a>
## <a name="types-of-providers"></a>Anbietertypen  
 Benutzeroberflächenautomatisierungs-Anbieter werden in zwei Kategorien unterteilt: clientseitige und serverseitige Anbieter.  
  
### <a name="client-side-providers"></a>Clientseitige Anbieter  
 Clientseitige Anbieter werden von Benutzeroberflächenautomatisierungs-Clients für die Kommunikation mit einer Anwendung implementiert, die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht oder nicht vollständig unterstützt. Client seitige Anbieter kommunizieren in der Regel über die Prozess Grenze hinweg mit dem Server, indem Sie Windows-Nachrichten senden und empfangen.  
  
 Da Benutzeroberflächenautomatisierungs-Anbieter für Steuerelemente in Win32-, Windows Forms-oder- [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Anwendungen als Teil des Betriebssystems bereitgestellt werden, müssen Client Anwendungen selten eigene Anbieter implementieren, und in dieser Übersicht werden Sie nicht näher behandelt.  
  
### <a name="server-side-providers"></a>Serverseitiger Anbieter  
 Server seitige Anbieter werden von benutzerdefinierten Steuerelementen oder Anwendungen implementiert, die auf einem anderen Benutzeroberflächen Framework als Win32, Windows Forms oder basieren [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .  
  
 Serverseitige Anbieter kommunizieren mit Clientanwendungen über Prozessgrenzen hinweg, indem sie Schnittstellen für das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kernsystem verfügbar machen, das wiederum Anforderungen von Clients bereitstellt.  
  
<a name="AutomationProviderConcepts"></a>
## <a name="ui-automation-provider-concepts"></a>Konzepte für Benutzeroberflächenautomatisierungs-Anbieter  
 Dieser Abschnitt bietet kurze Erläuterungen zu einer Auswahl von Schlüsselkonzepten, die Sie kennen müssen, um Benutzeroberflächenautomatisierungs-Anbieter implementieren zu können.  
  
### <a name="elements"></a>Elemente  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elemente sind Bestandteile der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , die für Benutzeroberflächenautomatisierungs-Clients angezeigt werden. Zu den entsprechenden Beispielen zählen Anwendungsfenster, Bereiche, Schaltflächen, QuickInfos, Listenfelder und Listenelemente.  
  
### <a name="navigation"></a>Navigation  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elemente werden für Clients als [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur verfügbar gemacht. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] erstellt die Struktur durch Navigieren von einem Element zu einem anderen. Die Navigation wird von den Anbietern für jedes Element aktiviert, von denen jedes möglicherweise auf ein übergeordnetes, gleichgeordnetes oder untergeordnetes Element verweist.  
  
 Weitere Informationen zur Clientansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Sichten  
 Ein Client kann die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur in drei hauptsächlichen Ansichten anzeigen, wie in der folgenden Tabelle dargestellt.  
  
|||  
|-|-|  
|Rohdatenansicht|Enthält alle Elemente.|  
|Steuerelementansicht|Enthält Elemente, die Steuerelemente sind.|  
|Inhaltsansicht|Enthält Elemente mit Inhalten.|  
  
 Weitere Informationen zu Clientansichten der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 Für die Definition eines Elements als Inhaltselement oder Steuerelement ist die Anbieterimplementierung zuständig. Steuerelemente können auch Inhaltselemente sein, aber alle Inhaltselemente sind auch Steuerelemente.  
  
### <a name="frameworks"></a>Frameworks  
 Ein Framework ist eine Komponente, die untergeordneten Steuerelemente, Treffertests und das Rendering in einem Bereich des Bildschirms verwaltet. Beispielsweise kann ein Win32-Fenster, das häufig als HWND bezeichnet wird, als Framework fungieren, das mehrere Elemente enthält, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] z. b. eine Menüleiste, eine Statusleiste und Schaltflächen.  
  
 Win32-Container Steuerelemente, z. b. Listenfelder und Struktur Ansichten, werden als Frameworks betrachtet, da Sie Ihren eigenen Code zum Rendern von untergeordneten Elementen und zum Ausführen von Treffer Tests enthalten. Im Gegensatz dazu ist ein [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Listenfeld kein Framework, da Rendering und Treffertests vom enthaltenen [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Fenster übernommen werden.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in einer Anwendung kann aus verschiedenen Frameworks bestehen. Beispielsweise kann ein HWND-Anwendungsfenster dynamisches HTML (DHTML) enthalten, das wiederum eine Komponente enthält, z. b. ein Kombinations Feld in einem HWND.  
  
### <a name="fragments"></a>Fragments  
 Ein Fragment ist eine vollständige Unterstruktur von Elementen eines bestimmten Frameworks. Das Element im Stammknoten der Unterstruktur wird als Fragmentstamm bezeichnet. Ein Fragmentstamm besitzt kein übergeordnetes Element, wird aber innerhalb eines anderen Frameworks gehostet, in der Regel in einem Win32-Fenster (HWND).  
  
### <a name="hosts"></a>Hosts  
 Der Stamm Knoten jedes Fragments muss in einem-Element gehostet werden, in der Regel in einem Win32-Fenster (HWND). Die Ausnahme stellt der Desktop dar, der in keinem anderen Element gehostet wird. Der Host eines benutzerdefinierten Steuerelements ist das HWND des Steuerelements selbst, nicht das Anwendungsfenster oder ein anderes Fenster, das möglicherweise Gruppen von Steuerelementen der obersten Ebene enthält.  
  
 Der Host eines Fragments spielt bei der Bereitstellung von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Diensten eine wichtige Rolle. Er ermöglicht die Navigation zum Fragmentstamm und stellt einige Standardeigenschaften bereit, damit diese nicht vom benutzerdefinierten Anbieter implementiert werden müssen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](server-side-ui-automation-provider-implementation.md)
