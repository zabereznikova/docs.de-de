---
title: 'Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c8c4f558386edd8da213f8a8af75b6a4c6a98b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft ein <xref:System.Windows.Controls.InkCanvas> in eine andere <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft mit einer Datenquelle.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 Das folgende Beispiel deklariert zwei <xref:System.Windows.Controls.InkCanvas> -Objekte in XAML und stellt die Datenbindung zwischen ihnen und anderen Datenquellen her.  Die erste <xref:System.Windows.Controls.InkCanvas>namens `ic`, mit zwei Datenquellen gebunden ist.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> und <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften auf `ic` gebunden <xref:System.Windows.Controls.ListBox> Objekte, die wiederum in der XAML-definierte Arrays gebunden sind.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, und <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaften des zweiten <xref:System.Windows.Controls.InkCanvas> gebunden sind mit dem ersten <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
