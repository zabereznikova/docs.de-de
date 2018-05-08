---
title: 'Gewusst wie: Programmgesteuertes Ändern der FlowDirection des Inhalts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: 97a64ad54384077a15a643dc528d043b2ef6627a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Gewusst wie: Programmgesteuertes Ändern der FlowDirection des Inhalts
Dieses Beispiel zeigt, wie Sie programmgesteuert ändern die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft von einem <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Beispiel  
 Zwei <xref:System.Windows.Controls.Button> Elemente erstellt werden, jeweils eine der möglichen Werte für darstellen <xref:System.Windows.FlowDirection>. Wenn eine Schaltfläche geklickt wird, wird der Wert der zugehörigen Eigenschaft mit dem Inhalt des angewendet eine <xref:System.Windows.Controls.FlowDocumentReader> mit dem Namen `tf1`.  Der Eigenschaftswert wird auch in geschrieben eine <xref:System.Windows.Controls.TextBlock> mit dem Namen `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Beispiel  
 Ereignisse im Zusammenhang mit den oben definierten Klicks auf Schaltflächen werden in einer C#-Code-Behind-Datei behandelt.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
