---
title: "Gewusst wie: Freigeben von Größeneigenschaften zwischen Grids"
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
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Gewusst wie: Freigeben von Größeneigenschaften zwischen Grids
In diesem Beispiel wird gezeigt, wie die größenanpassung Datengröße aller Spalten gemeinsam nutzen und zwischen Zeilen <xref:System.Windows.Controls.Grid> Elemente, um konsistente Größe zu halten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel führt zwei <xref:System.Windows.Controls.Grid> Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.DockPanel>. Die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> -Eigenschaft des <xref:System.Windows.Controls.Grid> wird auf das übergeordnete Element definiert <xref:System.Windows.Controls.DockPanel>.  
  
 Im Beispiel ändert den Wert der Eigenschaft mithilfe von zwei <xref:System.Windows.Controls.Button> Elemente; jedes Element stellt eine boolesche Eigenschaft Werte. Wenn der <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Eigenschaftswert festgelegt ist, um `true`, jedes Spalten- oder Mitglied einer <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> gemeinsam Informationen zur Größe, unabhängig von den Inhalt einer Zeile oder Spalte.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis ausgelöst wird. Das Beispiel schreibt die Ergebnisse dieser Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die in Beziehung mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
