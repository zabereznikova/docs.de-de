---
title: 'Vorgehensweise: Anzeigen von ListView-Inhalten mithilfe eines GridView-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910493"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Vorgehensweise: Anzeigen von ListView-Inhalten mithilfe eines GridView-Objekts
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
