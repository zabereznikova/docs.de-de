---
title: 'Vorgehensweise: Sicherstellen, dass ein GridSplitter sichtbar ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147146"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Vorgehensweise: Sicherstellen, dass ein GridSplitter sichtbar ist
Dieses Beispiel zeigt, wie Sie sicherstellen, eine <xref:System.Windows.Controls.GridSplitter> Steuerelement wird nicht von den anderen Steuerelementen im ausgeblendet eine <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Panel.Children%2A> von einem <xref:System.Windows.Controls.Grid> Steuerelement gerendert werden, in der Reihenfolge, die sie in Markup oder Code definiert sind. <xref:System.Windows.Controls.GridSplitter> Steuerelemente können von anderen Steuerelementen ausgeblendet werden, wenn Sie diese nicht als die letzten Elemente im Definieren der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung oder wenn Sie anderen Steuerelementen einen höheren <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Um zu verhindern, dass ausgeblendete <xref:System.Windows.Controls.GridSplitter> -Steuerelemente, führen Sie einen der folgenden.  
  
-   Stellen Sie sicher, dass <xref:System.Windows.Controls.GridSplitter> Steuerelemente sind die letzten <xref:System.Windows.Controls.Panel.Children%2A> hinzugefügt, die <xref:System.Windows.Controls.Grid>. Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> als das letzte Element in der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Legen Sie die <xref:System.Windows.Controls.Panel.ZIndexProperty> auf die <xref:System.Windows.Controls.GridSplitter> auf mehr als ein Steuerelement, das andernfalls verdecken würde. Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> steuern, eine höhere <xref:System.Windows.Controls.Panel.ZIndexProperty> als die <xref:System.Windows.Controls.Button> Steuerelement.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Festlegen von Rändern des Steuerelements, das andernfalls verdecken würde die <xref:System.Windows.Controls.GridSplitter> , damit die <xref:System.Windows.Controls.GridSplitter> verfügbar gemacht wird. Im folgenden Beispiel wird die Ränder auf ein Steuerelement, das andernfalls überlagern würde, und verbergen die <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridSplitter>
- [Gewusst wie-Themen](gridsplitter-how-to-topics.md)
