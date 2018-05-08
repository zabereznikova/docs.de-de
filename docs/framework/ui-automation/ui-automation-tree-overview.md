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
ms.openlocfilehash: 0823a569b19d46f32c1cb780470a935f20429c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-tree-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Struktur
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Hilfstechnologieprodukte und Testskripts navigieren der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur zum Sammeln von Informationen über die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] und die zugehörigen Elemente.  
  
 Innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur gibt es ist ein Stammelement (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), die den aktuellen Desktop darstellt und dessen untergeordnete Elemente Anwendungsfenstern. Jedes dieser untergeordneten Elemente kann Elemente, die Teile des darstellt enthalten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] wie Menüs, Schaltflächen, Symbolleisten und Listenfelder. Diese Elemente können wiederum Elemente, etwa Listeneinträge, enthalten.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist keine feststehende Struktur und wird selten vollständig angezeigt, da sie Tausende von Elementen enthalten kann. Teile der Struktur werden bei Bedarf erstellt, und die Struktur kann sich durch Hinzufügen, Verschieben oder Entfernen von Elementen ändern.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur durch Implementieren der Navigation zwischen Elementen innerhalb eines Fragments, das aus einem Stamm (in der Regel in einem Fenster gehostet) und einer Unterstruktur besteht. Anbieter sind jedoch nicht für die Navigation von einem Steuerelement zu einem anderen zuständig. Dies erfolgt durch die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core mithilfe von Informationen aus den Standardfensteranbietern.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Ansichten der Automatisierungsstruktur  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur kann gefiltert werden, um Ansichten zu erstellen, die nur die enthalten <xref:System.Windows.Automation.AutomationElement> für einen bestimmten Client relevanten Objekte. Dieser Ansatz ermöglicht es Clients, die Struktur, dargestellt durch Anpassen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] an ihre speziellen Anforderungen.  
  
 Ein Client hat zwei Möglichkeiten, die Ansicht anzupassen: durch Bereichsauswahl oder Filtern. Bei einer Bereichsauswahl wird der Umfang der Ansicht ausgehend von einem Basiselement definiert: Die Anwendung soll beispielsweise nur direkte untergeordnete Elemente des Desktops oder alle Nachfolgerelemente eines Anwendungsfensters suchen. Beim Filtern werden die Typen der Elemente angegeben, die in der Ansicht enthalten sein sollen.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen Filtern durch Definieren von Eigenschaften für Elemente, einschließlich der <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> und <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> Eigenschaften.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bietet drei Standardansichten. Diese Ansichten werden durch den Typ des ausgeführten Filterns definiert. Der Bereich jeder Ansicht wird durch die Anwendung definiert. Außerdem kann eine Anwendung andere Filter auf Eigenschaften anwenden, z. B. um nur aktivierte Steuerelemente in eine Steuerelementansicht aufzunehmen.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Rohdatenansicht  
 Die Rohdatenansicht des der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist die vollständige Struktur der <xref:System.Windows.Automation.AutomationElement> Objekte, die für den Stamm der Desktop ist. Die Rohdatenansicht orientiert sich stark an der programmatischen Struktur einer Anwendung und ist daher die ausführlichste verfügbare Ansicht. Sie stellt gleichzeitig die Basis zum Erstellen anderer Ansichten der Struktur dar. Da diese Sicht abhängig, für den zugrunde liegenden ist [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Framework, die Rohdatenansicht des eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Schaltfläche weist einen anderen Rohdatenansicht eine [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Schaltfläche.  
  
 Erhalten die Rohdatenansicht, indem Sie ohne Angabe von Eigenschaften nach Elementen suchen oder mit der <xref:System.Windows.Automation.TreeWalker.RawViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Steuerelementansicht  
 Der Steuerelementansicht der der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur vereinfacht die Hilfstechnologieprodukt Beschreibung der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] an die Endbenutzer und helfen diese Interaktion mit der Anwendung, da es eng zugeordnet der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Struktur ähnelt, die ein Endbenutzer sieht.  
  
 Die Steuerelementansicht ist eine Teilmenge der Rohdatenansicht. Sie enthält alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente aus der Rohdatenansicht, die ein Endbenutzer als interaktiv bzw. als Teil der logischen Struktur des Steuerelements in acht ansehen würde die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Beispiele für [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die an der logischen Struktur des beitragen der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], jedoch selbst nicht interaktiv sind, sind Elementcontainer wie listenansichtsheader, Symbolleisten, Menüs und die Statusleiste. Nicht interaktive Elemente, die nur für das Layout oder zur Dekoration verwendet werden, sind in der Steuerelementansicht nicht zu sehen. Ein Beispiel hierfür ist ein Bereich, der nur für das Layout der Steuerelemente in einem Dialogfeld verwendet wurde und selbst keine Informationen enthält. Nicht interaktive Elemente, die in der Steuerelementansicht angezeigt werden, sind Bilder mit Informationen sowie statischer Text in Dialogfeldern. Nicht interaktive Elemente, die in der Steuerelementansicht enthalten sind, können keinen Tastaturfokus erhalten.  
  
 Erhalten die Steuerelementansicht durch Suchen nach Elementen, die über die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> -Eigenschaftensatz auf `true`, oder indem Sie die <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Inhaltsansicht  
 Die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur ist eine Teilmenge der Steuerelementansicht. Er enthält [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die die tatsächlichen Informationen in einer Benutzeroberfläche vermitteln einschließlich [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Tastaturfokus Elemente, die empfangen kann, und etwas Text ein, die keine Bezeichnung auf eine [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Element. Beispielsweise werden die Werte aus einem Dropdown-Kombinationsfeld in der Inhaltsansicht angezeigt, da sie die vom Endbenutzer verwendeten Informationen darstellen. In der Inhaltsansicht ein Kombinationsfeld und Listenfeld sind beide dargestellt als eine Auflistung von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, in denen eine oder ggf. mehr als ein Element ausgewählt werden kann. Die Tatsache, dass ein Feld ständig geöffnet ist, und ein Feld erweitert und reduziert werden kann, spielt in der Inhaltsansicht keine Rolle, da sie dafür vorgesehen ist, die Daten bzw. den Inhalt anzuzeigen, der dem Benutzer angezeigt wird.  
  
 Erhalten die Inhaltsansicht durch Suchen nach Elementen, die über die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> -Eigenschaftensatz auf `true`, oder indem Sie die <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> in der Struktur navigieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Automation.AutomationElement>  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
