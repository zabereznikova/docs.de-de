---
title: 'Gewusst wie: Suchen nach einem Element anhand des Namens'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c51f22cb663b77ddcbbc280ab9d93c5e0eb7405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-an-element-by-its-name"></a>Gewusst wie: Suchen nach einem Element anhand des Namens
Dieses Beispiel beschreibt, wie die <xref:System.Windows.FrameworkElement.FindName%2A> Methode, um ein Element durch Ermitteln der <xref:System.Windows.FrameworkElement.Name%2A> Wert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Methode, die ein bestimmtes Element mit dem Namen ermitteln als Ereignishandler einer Schaltfläche geschrieben. `stackPanel`ist der <xref:System.Windows.FrameworkElement.Name%2A> des Stamms <xref:System.Windows.FrameworkElement> gesucht wird, und die visuell gibt das gefundene Element klicken Sie dann an, indem er als umgewandelt <xref:System.Windows.Controls.TextBlock> und Ändern eines der <xref:System.Windows.Controls.TextBlock> sichtbar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Eigenschaften.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
