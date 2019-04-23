---
title: Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 83643d8acea706bad439683702e4228d240b97bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090305"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen
In dieser Übersicht wird erläutert, die Reihenfolge der Rangfolge für Eigenschaften, mit denen Sie eine Spaltenüberschrift im Anpassen der <xref:System.Windows.Controls.GridView> Ansichtsmodus des eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Anpassen von einen Spaltenheader in einer GridView-Ansicht  
 Die Eigenschaften, die Inhalte, Layout und Stil, der eine Spaltenüberschrift im definieren, einer <xref:System.Windows.Controls.GridView> vielen verwandten Klassen gefunden werden. Einige dieser Eigenschaften verfügen, die ähnliche oder identische Funktionen.  
  
 Die Zeilen in der folgenden Tabelle zeigen die Gruppen von Eigenschaften, die die gleiche Funktion ausführen. Können Sie diese Eigenschaften anpassen, die Spaltenüberschriften in einer <xref:System.Windows.Controls.GridView>. Die Reihenfolge für die zugehörigen Eigenschaften ist von rechts nach links, in dem die Eigenschaft in der äußersten rechten Spalte die höchste Priorität hat. Z. B. wenn ein <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> festgelegt ist, auf die <xref:System.Windows.Controls.GridViewColumnHeader> Objekt und die <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> ist für das zugeordnete <xref:System.Windows.Controls.GridViewColumn>, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> hat Vorrang vor. In diesem Szenario die <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> hat keine Auswirkungen.  
  
 **Verknüpfte Eigenschaften für Spaltenüberschriften in einer GridView-Ansicht**  
  
|||||  
|-|-|-|-|  
|**Klassen**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Menü-Kontexteigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**QuickInfo**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Header-Vorlage**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Style-Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>für **Vorlage Headereigenschaften**, setzen Sie die Vorlage und den Eigenschaften der Auswahl, die Vorlage Eigenschaft hat Vorrang. Z. B., wenn Sie beide Optionen festlegen der <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> und <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Eigenschaften, die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft austauschverarbeitungsmodi Vorrang vor.  
  
## <a name="see-also"></a>Siehe auch

- [Themen zu Vorgehensweisen](listview-how-to-topics.md)
- [Übersicht über ListView](listview-overview.md)
- [Übersicht über GridView](gridview-overview.md)
