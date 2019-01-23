---
title: 'Vorgehensweise: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dd347781451c9e574fed97c1a553c25bda1b8d7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545396"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Vorgehensweise: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader
Dieses Beispiel zeigt, wie Sie das Erscheinungsbild eines gezogenen <xref:System.Windows.Controls.GridViewColumnHeader> Wenn der Benutzer die Position einer Spalte ändert.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine Spaltenüberschrift ziehen, an einen anderen Speicherort in einen <xref:System.Windows.Controls.ListView> , verwendet <xref:System.Windows.Controls.GridView> für den Ansichtsmodus an, die für die Spalte an die neue Position verschoben wird. Während Sie die Kopfzeile der Spalte ziehen, wird eine schwebende Kopie des Headers zusätzlich zu der ursprünglichen Überschrift angezeigt. Einen Spaltenkopf in einem <xref:System.Windows.Controls.GridView> durch dargestellt wird ein <xref:System.Windows.Controls.GridViewColumnHeader> Objekt.  
  
 Sie können zum Anpassen der Darstellung der Gleitkomma- und der ursprüngliche Header festlegen <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Diese <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> angewendet werden, wenn die <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert ist `true` und <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> Eigenschaftswert ist <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Wenn der Benutzer die Maustaste drückt und gedrückt hält, während der Mauszeiger über die <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> -Eigenschaftswert auf `true`. Ebenso, wenn der Benutzer beginnt der Ziehvorgang, der <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> eigenschaftsänderungen <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Das folgende Beispiel zeigt, wie festgelegt <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.Background%2A> Farben, der die ursprünglichen und unverankerte-Header, wenn der Benutzer eine Spalte zu einer neuen Position zieht.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
