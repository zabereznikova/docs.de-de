---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Struktur
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
ms.openlocfilehash: a0b888e8ecc80e3739c583931a86da3cdb7242d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179451"
---
# <a name="ui-automation-tree-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Struktur
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Hilfstechnologieprodukte und Testskripts navigieren durch die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur, um Informationen über die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] und deren Elemente zu sammeln.  
  
 Innerhalb [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] der Struktur befindet sich<xref:System.Windows.Automation.AutomationElement.RootElement%2A>ein Stammelement ( ), das den aktuellen Desktop darstellt und dessen untergeordnete Elemente Anwendungsfenster darstellen. Jedes dieser untergeordneten Elemente kann Elemente enthalten, die Komponenten der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] darstellen, z. B. Menüs, Schaltflächen, Symbolleisten und Listenfelder. Diese Elemente können wiederum Elemente, etwa Listeneinträge, enthalten.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur ist keine feststehende Struktur und wird selten vollständig angezeigt, da sie Tausende von Elementen enthalten kann. Teile der Struktur werden bei Bedarf erstellt, und die Struktur kann sich durch Hinzufügen, Verschieben oder Entfernen von Elementen ändern.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur durch Implementieren der Navigation zwischen Elementen innerhalb eines Fragments, das aus einem Stamm (in der Regel in einem Fenster gehostet) und einer Unterstruktur besteht. Anbieter sind jedoch nicht für die Navigation von einem Steuerelement zu einem anderen zuständig. Dies wird vom [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Kern verwaltet, der dazu Informationen von den Standardfensteranbietern verwendet.  
  
<a name="uiautomation_tree_view"></a>
## <a name="views-of-the-automation-tree"></a>Ansichten der Automatisierungsstruktur  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur kann gefiltert werden, um Ansichten zu erstellen, die nur die für einen bestimmten Client relevanten <xref:System.Windows.Automation.AutomationElement>-Objekte enthalten. Dieser Ansatz ermöglicht es Clients, die durch [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dargestellte Struktur an ihre speziellen Anforderungen anzupassen.  
  
 Ein Client hat zwei Möglichkeiten, die Ansicht anzupassen: durch Bereichsauswahl oder Filtern. Bei einer Bereichsauswahl wird der Umfang der Ansicht ausgehend von einem Basiselement definiert: Die Anwendung soll beispielsweise nur direkte untergeordnete Elemente des Desktops oder alle Nachfolgerelemente eines Anwendungsfensters suchen. Beim Filtern werden die Typen der Elemente angegeben, die in der Ansicht enthalten sein sollen.  
  
 Benutzeroberflächenautomatisierungs-Anbieter unterstützen Filtern durch Definieren von Eigenschaften für Elemente, einschließlich der <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>-Eigenschaft und der <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>-Eigenschaft.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bietet drei Standardansichten. Diese Ansichten werden durch den Typ des ausgeführten Filterns definiert. Der Bereich jeder Ansicht wird durch die Anwendung definiert. Außerdem kann eine Anwendung andere Filter auf Eigenschaften anwenden, z. B. um nur aktivierte Steuerelemente in eine Steuerelementansicht aufzunehmen.  
  
<a name="uiautomation_raw_view"></a>
### <a name="raw-view"></a>Rohdatenansicht  
 Die Rohdatenansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur ist die vollständige Struktur der <xref:System.Windows.Automation.AutomationElement>-Objekte, deren Stamm der Desktop ist. Die Rohdatenansicht orientiert sich stark an der programmatischen Struktur einer Anwendung und ist daher die ausführlichste verfügbare Ansicht. Sie stellt gleichzeitig die Basis zum Erstellen anderer Ansichten der Struktur dar. Da diese Ansicht vom [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zugrunde liegenden Framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] abhängt, hat die unformatierte Ansicht einer Schaltfläche eine andere unformatierte Ansicht als eine Win32-Schaltfläche.  
  
 Sie erhalten die Rohdatenansicht, indem Sie ohne Angabe von Eigenschaften nach Elementen suchen oder mit <xref:System.Windows.Automation.TreeWalker.RawViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_control_view"></a>
### <a name="control-view"></a>Steuerelementansicht  
 Die Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur vereinfacht die Aufgabe von Hilfstechnologieprodukten, dem Endbenutzer die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zu beschreiben und ihn bei der Interaktion mit der Anwendung zu unterstützen, da diese Ansicht sehr der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Struktur ähnelt, die ein Endbenutzer sieht.  
  
 Die Steuerelementansicht ist eine Teilmenge der Rohdatenansicht. Sie enthält alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elemente aus der Rohdatenansicht, die ein Endbenutzer als interaktiv bzw. als Teil der logischen Struktur des Steuerelements in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ansehen würde. Beispiele für [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elemente, die zur logischen Struktur der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] beitragen, jedoch selbst nicht interaktiv sind, sind Elementcontainer wie Listenansichtsheader, Symbolleisten, Menüs und die Statusleiste. Nicht interaktive Elemente, die nur für das Layout oder zur Dekoration verwendet werden, sind in der Steuerelementansicht nicht zu sehen. Ein Beispiel hierfür ist ein Bereich, der nur für das Layout der Steuerelemente in einem Dialogfeld verwendet wurde und selbst keine Informationen enthält. Nicht interaktive Elemente, die in der Steuerelementansicht angezeigt werden, sind Bilder mit Informationen sowie statischer Text in Dialogfeldern. Nicht interaktive Elemente, die in der Steuerelementansicht enthalten sind, können keinen Tastaturfokus erhalten.  
  
 Sie erhalten die Steuerelementansicht, indem Sie nach Elementen suchen, deren <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>-Eigenschaft auf `true` festgelegt ist, oder indem Sie über <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> in der Struktur navigieren.  
  
<a name="uiautomation_content_view"></a>
### <a name="content-view"></a>Inhaltsansicht  
 Die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Struktur ist eine Teilmenge der Steuerelementansicht. Sie enthält [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elemente, die die tatsächlichen Informationen in einer Benutzeroberfläche mitteilen, einschließlich [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elementen, die den Tastaturfokus erhalten können, und einigen Texten, die keine Bezeichnungen für ein [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Element sind. Beispielsweise werden die Werte aus einem Dropdown-Kombinationsfeld in der Inhaltsansicht angezeigt, da sie die vom Endbenutzer verwendeten Informationen darstellen. In der Inhaltsansicht wird sowohl ein Kombinationsfeld als auch ein Listenfeld als Auflistung von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elementen dargestellt, wobei mindestens ein Element ausgewählt werden kann. Die Tatsache, dass ein Feld ständig geöffnet ist und ein Feld erweitert und reduziert werden kann, spielt in der Inhaltsansicht keine Rolle, da sie dafür vorgesehen ist, die Daten bzw. den Inhalt anzuzeigen, der dem Benutzer angezeigt wird.  
  
 Sie erhalten die Inhaltsansicht, indem Sie nach Elementen suchen, deren <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>-Eigenschaft auf `true` festgelegt ist, oder indem Sie über <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> in der Struktur navigieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.AutomationElement>
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
