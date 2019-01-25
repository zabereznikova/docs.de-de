---
title: 'Vorgehensweise: Binden eines Listenfelds an Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 6d37cda057ea1e7ca6761363857a2647da37afee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650651"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Vorgehensweise: Binden eines Listenfelds an Daten
Erstellen Sie ein Anwendungsentwickler kann <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt. Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.ListBox> auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente durch die Datenbindung an eine Datenquelle namens *Farben*. In diesem Fall ist es nicht erforderlich, mit <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
