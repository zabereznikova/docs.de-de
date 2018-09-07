---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Struktur
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 042f3f82a88e987131145f38c1d8f5ecfa8dc487
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067486"
---
# <a name="ui-automation-tree-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Struktur
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Hilfstechnologieprodukte und Testskripts navigieren die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur zum Sammeln von Informationen über die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] und die zugehörigen Elemente.  
  
 In der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur vorhanden ist, ein Stammelement (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), das den aktuellen Desktop darstellt und dessen untergeordnete Elemente Anwendungsfenstern. Jedes dieser untergeordneten Elemente kann Elemente, die Teile enthalten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] wie z. B. Menüs, Schaltflächen, Symbolleisten und Listenfelder. Diese Elemente können wiederum Elemente, etwa Listeneinträge, enthalten.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist nicht festgelegt und wird selten vollständig angezeigt, da sie Tausende von Elementen enthalten kann. Teile der Struktur werden bei Bedarf erstellt, und die Struktur kann sich durch Hinzufügen, Verschieben oder Entfernen von Elementen ändern.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur durch Implementieren der Navigation zwischen Elementen innerhalb eines Fragments, das aus einem Stamm (in der Regel in einem Fenster gehostet) und einer Unterstruktur besteht. Anbieter sind jedoch nicht für die Navigation von einem Steuerelement zu einem anderen zuständig. Dies wird von verwaltet die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Kern mit Informationen von den Standardfensteranbietern.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Ansichten der Automatisierungsstruktur  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur kann gefiltert werden, um Ansichten zu erstellen, die nur die enthalten <xref:System.Windows.Automation.AutomationElement> für einen bestimmten Client relevanten Objekte. Dieser Ansatz ermöglicht es Clients, die zum Anpassen der Struktur durch angezeigt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] an ihre speziellen Anforderungen.  
  
 Ein Client hat zwei Möglichkeiten, die Ansicht anzupassen: durch Bereichsauswahl oder Filtern. Bei einer Bereichsauswahl wird der Umfang der Ansicht ausgehend von einem Basiselement definiert: Die Anwendung soll beispielsweise nur direkte untergeordnete Elemente des Desktops oder alle Nachfolgerelemente eines Anwendungsfensters suchen. Beim Filtern werden die Typen der Elemente angegeben, die in der Ansicht enthalten sein sollen.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen Filtern durch Definieren von Eigenschaften für Elemente, einschließlich der <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> und <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> Eigenschaften.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stellt drei Standardansichten bereit. Diese Ansichten werden durch den Typ des ausgeführten Filterns definiert. Der Bereich jeder Ansicht wird durch die Anwendung definiert. Außerdem kann eine Anwendung andere Filter auf Eigenschaften anwenden, z. B. um nur aktivierte Steuerelemente in eine Steuerelementansicht aufzunehmen.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Rohdatenansicht  
 Die Rohdatenansicht des der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist die vollständige Struktur der <xref:System.Windows.Automation.AutomationElement> Objekte, die den Stamm der Desktop ist. Die Rohdatenansicht orientiert sich stark an der programmatischen Struktur einer Anwendung und ist daher die ausführlichste verfügbare Ansicht. Sie stellt gleichzeitig die Basis zum Erstellen anderer Ansichten der Struktur dar. Da diese Sicht abhängig, für den zugrunde liegenden ist [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Framework, die Rohdatenansicht des eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Schaltfläche weist eine andere unformatierte Ansicht als ein [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Schaltfläche.  
  
 Die Rohdatenansicht abgerufen wird, durch die Suche nach Elementen ohne Angabe von Eigenschaften oder mithilfe der <xref:System.Windows.Automation.TreeWalker.RawViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Steuerelementansicht  
 Der Steuerelementansicht der der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur vereinfacht die Hilfstechnologieprodukten, die beschreibt die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] für den Benutzer und dabei Interaktion des Endbenutzers mit der Anwendung, da es genau ist die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Struktur durch einen Endbenutzer angesehen.  
  
 Die Steuerelementansicht ist eine Teilmenge der Rohdatenansicht. Sie enthält alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente aus der Rohdatenansicht, die ein Endbenutzer als interaktiv bzw. als Teil der logischen Struktur des Steuerelements in ansehen würde die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Beispiele für [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die der logischen Struktur des beitragen die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], jedoch selbst nicht interaktiv sind, sind Elementcontainer wie listenansichtsheader, Symbolleisten, Menüs und der Statusleiste angezeigt. Nicht interaktive Elemente, die nur für das Layout oder zur Dekoration verwendet werden, sind in der Steuerelementansicht nicht zu sehen. Ein Beispiel hierfür ist ein Bereich, der nur für das Layout der Steuerelemente in einem Dialogfeld verwendet wurde und selbst keine Informationen enthält. Nicht interaktive Elemente, die in der Steuerelementansicht angezeigt werden, sind Bilder mit Informationen sowie statischer Text in Dialogfeldern. Nicht interaktive Elemente, die in der Steuerelementansicht enthalten sind, können keinen Tastaturfokus erhalten.  
  
 Ansicht des Steuerelement wird abgerufen, indem Sie die Suche nach Elementen, die die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> -Eigenschaftensatz auf `true`, oder mithilfe der <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Inhaltsansicht  
 Der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist eine Teilmenge der Steuerelementansicht. Es enthält [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die die tatsächlichen Informationen in einer Benutzeroberfläche zu vermitteln einschließlich [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Tastaturfokus Elemente, die empfangen kann, und Text, der keiner Bezeichnung auf eine [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Element. Beispielsweise werden die Werte aus einem Dropdown-Kombinationsfeld in der Inhaltsansicht angezeigt, da sie die vom Endbenutzer verwendeten Informationen darstellen. In der Ansicht "Inhalt", ein Kombinationsfeld und Listenfeld werden sowohl dargestellt als eine Auflistung von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, 1 oder vielleicht mehr als 1 Element ausgewählt werden kann. Die Tatsache, dass ein Feld ständig geöffnet ist, und ein Feld erweitert und reduziert werden kann, spielt in der Inhaltsansicht keine Rolle, da sie dafür vorgesehen ist, die Daten bzw. den Inhalt anzuzeigen, der dem Benutzer angezeigt wird.  
  
 Die Ansicht "Inhalt" wird abgerufen, indem Sie die Suche nach Elementen, die die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> -Eigenschaftensatz auf `true`, oder mithilfe der <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> in der Struktur navigieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Automation.AutomationElement>  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
