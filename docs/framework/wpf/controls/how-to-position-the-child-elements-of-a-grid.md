---
title: 'Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters'
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
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters
In diesem Beispiel wird gezeigt, wie auf die Get- und set-Methoden, die auf definiert <xref:System.Windows.Controls.Grid> um untergeordnete Elemente zu positionieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert ein übergeordnetes Element <xref:System.Windows.Controls.Grid> Element (`grid1`), besitzt drei Spalten und drei Zeilen. Ein untergeordnetes Element <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) hinzugefügt wird, um die <xref:System.Windows.Controls.Grid> Spalte Position 0 (null), Zeile Position 0 (null). <xref:System.Windows.Controls.Button>Elemente darstellen, Methoden, die aufgerufen werden können, um die Position der <xref:System.Windows.Shapes.Rectangle> Element innerhalb der <xref:System.Windows.Controls.Grid>. Wenn ein Benutzer eine Schaltfläche klickt, wird die entsprechende Methode aktiviert.  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Auslösen von Ereignissen. Das Beispiel schreibt diese Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die in Beziehung mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Grid>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
