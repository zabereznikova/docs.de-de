---
title: 'Vorgehensweise: Anzeigen von ListView-Inhalten mit GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 1066869c80bf5bd87d656bcb4994c188ee0e8efc
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185609"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Vorgehensweise: Anzeigen von ListView-Inhalten mit GridView
Dieses Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Sie können den Anzeigemodus der definieren eine <xref:System.Windows.Controls.GridView> durch Angabe <xref:System.Windows.Controls.GridViewColumn> Objekte. Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.GridViewColumn> Objekte, die an den Inhalt der Daten zu binden, die für angegeben wird die <xref:System.Windows.Controls.ListView> Steuerelement. Dies <xref:System.Windows.Controls.GridView> Beispiel gibt drei <xref:System.Windows.Controls.GridViewColumn> Objekte, die zugeordnet, der `FirstName`, `LastName`, und `EmployeeNumber` Felder der `EmployeeInfoDataSource` , festgelegt ist, als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von der <xref:System.Windows.Controls.ListView> Steuerelement.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die folgende Abbildung zeigt, wie in diesem Beispiel wird angezeigt.  
  
 ![Screenshot mit einer ListView mit GridView-Ausgabe.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Übersicht über ListView](listview-overview.md)
- [Übersicht über GridView](gridview-overview.md)
- [Themen zu Vorgehensweisen](listview-how-to-topics.md)
