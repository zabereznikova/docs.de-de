---
title: 'Vorgehensweise: Suchen nach einem Element anhand des Namens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: 7405f9ba8db5d4db0ce35ca250f13e456685f39b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351045"
---
# <a name="how-to-find-an-element-by-its-name"></a>Vorgehensweise: Suchen nach einem Element anhand des Namens
In diesem Beispiel wird beschrieben, wie Sie mit der <xref:System.Windows.FrameworkElement.FindName%2A> Methode zum Suchen von einem Element anhand seiner <xref:System.Windows.FrameworkElement.Name%2A> Wert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Methode, die ein bestimmtes Element anhand des Namens suchen als Ereignishandler einer Schaltfläche geschrieben. `stackPanel` ist der <xref:System.Windows.FrameworkElement.Name%2A> des Stamms <xref:System.Windows.FrameworkElement> durchsucht wird, und der Beispielmethode zeigt das gefundene Element dann an, durch das umwandeln, als <xref:System.Windows.Controls.TextBlock> und Ändern eines der <xref:System.Windows.Controls.TextBlock> sichtbar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Eigenschaften.  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
