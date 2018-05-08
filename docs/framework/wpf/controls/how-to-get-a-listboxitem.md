---
title: 'Gewusst wie: Abrufen eines ListBoxItem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: f1e25ce60ff5feb8fd644a5864dbd762b4b5fa39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-a-listboxitem"></a>Gewusst wie: Abrufen eines ListBoxItem
Wenn Sie einen bestimmten abrufen müssen <xref:System.Windows.Controls.ListBoxItem> an einem bestimmten Index in einem <xref:System.Windows.Controls.ListBox>, können Sie eine <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ListBox> und der zugehörigen Elemente.  
  
 [!code-xaml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 Im folgende Beispiel wird gezeigt, wie das Element abzurufender den Index des Elements in der <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> Eigenschaft von der <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Nachdem Sie das Listenfeldelement abgerufen haben, können Sie den Inhalt des Elements, anzeigen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
