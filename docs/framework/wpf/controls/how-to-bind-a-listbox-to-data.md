---
title: 'Vorgehensweise: Binden eines ListBox-Objekts an Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911156"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Vorgehensweise: Binden eines ListBox-Objekts an Daten
Erstellen Sie ein Anwendungsentwickler kann <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt. Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.ListBox> auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente durch die Datenbindung an eine Datenquelle namens *Farben*. In diesem Fall ist es nicht erforderlich, mit <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Steuerelemente](../advanced/optimizing-performance-controls.md)
