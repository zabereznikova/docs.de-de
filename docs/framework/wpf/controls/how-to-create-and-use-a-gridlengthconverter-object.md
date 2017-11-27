---
title: 'Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 775d51a35f64f8736931dec32fb439bb9925be53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.GridLengthConverter>. Im Beispiel definiert eine benutzerdefinierte Methode wird aufgerufen, `changeCol`, übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.GridLengthConverter> , konvertiert der <xref:System.Windows.Controls.ContentControl.Content%2A> des eine <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Windows.GridLength>. Der konvertierte Wert wird dann wieder als Wert des übergeben der <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Eigenschaft von der <xref:System.Windows.Controls.ColumnDefinition> Element.  
  
 Im Beispiel definiert auch eine zweite benutzerdefinierte Methode namens `changeColVal`. Diese benutzerdefinierte Methode konvertiert die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> des eine <xref:System.Windows.Controls.Slider> auf eine <xref:System.String> und übergibt dann, den Wert zum Sichern der <xref:System.Windows.Controls.ColumnDefinition> als die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> des Elements.  
  
 Beachten Sie, dass eine Separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei definiert den Inhalt einer <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.GridLengthConverter>  
 <xref:System.Windows.GridLength>
