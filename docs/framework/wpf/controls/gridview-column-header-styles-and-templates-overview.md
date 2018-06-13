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
ms.openlocfilehash: 28b4a64a6c79b226b1ff4b3bfcbf9a55b6d8df78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553870"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen
In dieser Übersicht wird erläutert, die Reihenfolge der Rangfolge für Eigenschaften, mit denen Sie eine Spaltenüberschrift im Anpassen der <xref:System.Windows.Controls.GridView> Ansichtsmodus des ein <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Anpassen einer Spaltenüberschrift in einer GridView  
 Die Eigenschaften, die Inhalte, Layout und Stil Rand eines Spaltenheaders im definieren, einer <xref:System.Windows.Controls.GridView> auf vielen verwandten Klassen gefunden werden. Einige dieser Eigenschaften aufweisen, die Ähnlichkeit oder identische Funktionen.  
  
 Die Zeilen in der folgenden Tabelle angezeigt werden Gruppen von Eigenschaften, die die gleiche Funktion ausführen. Können diese Eigenschaften anpassen, die Spaltenüberschriften in einer <xref:System.Windows.Controls.GridView>. Rangfolge bei verwandten Eigenschaften ist, in dem die höchste Priorität hat der Eigenschaft in der äußersten rechten Spalte von rechts nach links. Z. B. wenn ein <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> festgelegt ist, auf die <xref:System.Windows.Controls.GridViewColumnHeader> Objekt und die <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> ist auf dem zugeordneten <xref:System.Windows.Controls.GridViewColumn>, die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> hat Vorrang vor. In diesem Szenario die <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> hat keine Auswirkungen.  
  
 **Verwandte Eigenschaften für die Spaltenüberschriften in einer GridView**  
  
|||||  
|-|-|-|-|  
|**Klassen**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Menü-Kontexteigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**QuickInfo**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Header-Vorlage**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Style-Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>für **Vorlage Headereigenschaften**, wenn Sie, die Vorlage und den Selektor Vorlageneigenschaften, die Vorlage Eigenschaft hat Vorrang festlegen. Angenommen, wenn Sie beide Optionen festlegen der <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> und <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Eigenschaften, die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Eigenschaft Vorrang.  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
