---
title: "&#220;bersicht &#252;ber die Benutzeroberfl&#228;chenautomatisierungs-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Automatisierungsstruktur"
  - "UI-Automatisierung, Struktur"
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# &#220;bersicht &#252;ber die Benutzeroberfl&#228;chenautomatisierungs-Struktur
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler, die die verwaltete verwenden möchten vorgesehen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Klassen, die in der <xref:System.Windows.Automation> Namespace. Die neuesten Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows Automation API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Hilfstechnologieprodukte und Testskripts navigieren die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur zum Sammeln von Informationen über die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] und seine Elemente.  
  
 Innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur vorhanden ist, ein Stammelement (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), das den aktuellen Desktop darstellt und dessen untergeordneten Elemente darstellen Anwendungsfenster. Jedes dieser untergeordneten Elemente kann Elemente, Teile enthalten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] wie Menüs, Schaltflächen, Symbolleisten und Listenfelder. Diese Elemente können wiederum Elemente, etwa Listeneinträge, enthalten.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist nicht festgelegt und wird selten vollständig angezeigt, da sie Tausende von Elementen enthalten kann. Teile der Struktur werden bei Bedarf erstellt, und die Struktur kann sich durch Hinzufügen, Verschieben oder Entfernen von Elementen ändern.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützt die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur durch Implementierung von Navigation zwischen Elementen in einem Fragment, bestehend aus einem Stamm (in der Regel in einem Fenster gehostet) und einer Teilstruktur. Anbieter sind jedoch nicht für die Navigation von einem Steuerelement zu einem anderen zuständig. Dies erfolgt durch die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kern unter Verwendung von Informationen aus der Standardfensteranbieter.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Ansichten der Automatisierungsstruktur  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur kann gefiltert werden, um Ansichten zu erstellen, die nur die enthalten <xref:System.Windows.Automation.AutomationElement> für einen bestimmten Client relevanten Objekte. Dieser Ansatz ermöglicht, die über dargestellte Struktur anpassen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] auf ihre Bedürfnisse.  
  
 Ein Client hat zwei Möglichkeiten, die Ansicht anzupassen: durch Bereichsauswahl oder Filtern. Bei einer Bereichsauswahl wird der Umfang der Ansicht ausgehend von einem Basiselement definiert: Die Anwendung soll beispielsweise nur direkte untergeordnete Elemente des Desktops oder alle Nachfolgerelemente eines Anwendungsfensters suchen. Beim Filtern werden die Typen der Elemente angegeben, die in der Ansicht enthalten sein sollen.  
  
 Benutzeroberflächenautomatisierungs-Anbietern unterstützen Filtern durch die Definition von Eigenschaften für Elemente, einschließlich der <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> und <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> Eigenschaften.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]stellt drei Standardansichten bereit. Diese Ansichten werden durch den Typ des ausgeführten Filterns definiert. Der Bereich jeder Ansicht wird durch die Anwendung definiert. Außerdem kann eine Anwendung andere Filter auf Eigenschaften anwenden, z. B. um nur aktivierte Steuerelemente in eine Steuerelementansicht aufzunehmen.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Rohdatenansicht  
 Die Rohdatenansicht des der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist die vollständige Struktur der <xref:System.Windows.Automation.AutomationElement> Objekte, die den Stamm der Desktop ist. Die Rohdatenansicht orientiert sich stark an der programmatischen Struktur einer Anwendung und ist daher die ausführlichste verfügbare Ansicht. Sie stellt gleichzeitig die Basis zum Erstellen anderer Ansichten der Struktur dar. Da in dieser Ansicht der zugrunde liegenden abhängt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Framework, die Rohdatenansicht des ein [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Schaltfläche haben eine unterschiedliche Rohdatenansicht eine [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Schaltfläche.  
  
 Die Rohdatenansicht abgerufen wird, ohne Angabe von Eigenschaften nach Elementen suchen oder mit der <xref:System.Windows.Automation.TreeWalker.RawViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Steuerelementansicht  
 Der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur vereinfacht das Hilfstechnologieprodukt beschreiben die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] auf die Endbenutzer und Unterstützung Interaktion des Endbenutzers mit der Anwendung, da sie eng zugeordnet wird die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Struktur, die von einem Endbenutzer wahrgenommen.  
  
 Die Steuerelementansicht ist eine Teilmenge der Rohdatenansicht. Sie enthält alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente aus der Rohdatenansicht, die ein Endbenutzer als interaktiv bzw. als Teil der logischen Struktur des Steuerelements in ansehen würden die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Beispiele für [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die die logische Struktur beeinflussen die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], aber nicht interaktive selbst sind, Elementcontainer wie Listenansichtheader, Symbolleisten, Menüs und der Statusleiste. Nicht interaktive Elemente, die nur für das Layout oder zur Dekoration verwendet werden, sind in der Steuerelementansicht nicht zu sehen. Ein Beispiel hierfür ist ein Bereich, der nur für das Layout der Steuerelemente in einem Dialogfeld verwendet wurde und selbst keine Informationen enthält. Nicht interaktive Elemente, die in der Steuerelementansicht angezeigt werden, sind Bilder mit Informationen sowie statischer Text in Dialogfeldern. Nicht interaktive Elemente, die in der Steuerelementansicht enthalten sind, können keinen Tastaturfokus erhalten.  
  
 Die Control View erhalten Sie durch Suchen nach Elementen, die über die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> -Eigenschaft auf festgelegt `true`, oder mithilfe der <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Inhaltsansicht  
 Die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur ist eine Teilmenge der Steuerelementansicht. Es enthält [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, die in einer Benutzeroberfläche, die true Informationen vermitteln einschließlich [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Tastaturfokus Elemente, die empfangen kann, und Text, der keiner Bezeichnung auf eine [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Element. Beispielsweise werden die Werte aus einem Dropdown-Kombinationsfeld in der Inhaltsansicht angezeigt, da sie die vom Endbenutzer verwendeten Informationen darstellen. In der Inhaltsansicht ein Kombinationsfeld und Listenfeld sind beide dargestellt als eine Auflistung von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente, wobei&1; oder vielleicht mehr als&1; Element ausgewählt werden kann. Die Tatsache, dass ein Feld ständig geöffnet ist, und ein Feld erweitert und reduziert werden kann, spielt in der Inhaltsansicht keine Rolle, da sie dafür vorgesehen ist, die Daten bzw. den Inhalt anzuzeigen, der dem Benutzer angezeigt wird.  
  
 Die Inhaltsansicht wird abgerufen, indem die Suche nach Elementen, die über die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> Eigenschaft festgelegt, um `true`, oder mithilfe der <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> in der Struktur navigieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Automation.AutomationElement>   
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)