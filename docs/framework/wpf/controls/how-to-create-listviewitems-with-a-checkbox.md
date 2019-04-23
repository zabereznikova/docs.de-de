---
title: 'Vorgehensweise: Erstellen von ListViewItems mit einem Kontrollkästchen'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083104"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Vorgehensweise: Erstellen von ListViewItems mit einem Kontrollkästchen
In diesem Beispiel wird veranschaulicht, wie eine Spalte mit angezeigt <xref:System.Windows.Controls.CheckBox> -Steuerelemente in eine <xref:System.Windows.Controls.ListView> -Steuerelements, verwendet eine <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Beispiel  
 Um eine Spalte zu erstellen, enthält <xref:System.Windows.Controls.CheckBox> -Steuerelemente in einer <xref:System.Windows.Controls.ListView>, erstellen eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> von einer <xref:System.Windows.Controls.GridViewColumn> auf die <xref:System.Windows.DataTemplate>.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Im Beispiel wird die <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> Eigenschaft der <xref:System.Windows.Controls.CheckBox> auf die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.ListViewItem> , die Sie enthält. Aus diesem Grund, wenn die <xref:System.Windows.Controls.ListViewItem> , enthält die <xref:System.Windows.Controls.CheckBox> ausgewählt ist, die <xref:System.Windows.Controls.CheckBox> aktiviert ist.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 Das folgende Beispiel zeigt, wie zum Erstellen einer Spalte des <xref:System.Windows.Controls.CheckBox> Steuerelemente. Zu der Spalte, die im Beispiel wird die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.GridViewColumn> auf die <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Übersicht über ListView](listview-overview.md)
- [Themen zu Vorgehensweisen](listview-how-to-topics.md)
- [Übersicht über GridView](gridview-overview.md)
