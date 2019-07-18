---
title: 'Vorgehensweise: Freigeben von Größeneigenschaften zwischen Rastern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910584"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Vorgehensweise: Freigeben von Größeneigenschaften zwischen Rastern
In diesem Beispiel wird gezeigt, wie zum Freigeben der Größenänderungsdaten von Spalten und Zeilen zwischen <xref:System.Windows.Controls.Grid> Elemente, um konsistente Größe beibehalten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel führt zwei <xref:System.Windows.Controls.Grid> -Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.DockPanel>. Die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> angefügte Eigenschaft von <xref:System.Windows.Controls.Grid> wird auf dem übergeordneten Element definiert <xref:System.Windows.Controls.DockPanel>.  
  
 Im Beispiel wird der Eigenschaftswert geändert, mithilfe von zwei <xref:System.Windows.Controls.Button> Elemente; jedes Element steht für eine der booleschen Eigenschaftswerte. Wenn die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Eigenschaftswert wird festgelegt, um `true`, jedes Spalten- oder Mitglied einer <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> -Eigenschaft größenänderungsinformationen, unabhängig vom Inhalt einer Zeile oder Spalte.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis auslöst. Das Beispiel schreibt die Ergebnisse dieser Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die Verwendung im Zusammenhang mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
