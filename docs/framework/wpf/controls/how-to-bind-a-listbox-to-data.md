---
title: 'Gewusst wie: Binden eines Listenfelds an Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: deb5e05a7c48f26d0b829ba75b4ae120841e0a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-listbox-to-data"></a>Gewusst wie: Binden eines Listenfelds an Daten
Ein Anwendungsentwickler kann erstellen <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt. Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.ListBox> , auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente nach dem Datenbindung an eine Datenquelle namens *Farben*. In diesem Fall ist es nicht notwendig, verwenden <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
