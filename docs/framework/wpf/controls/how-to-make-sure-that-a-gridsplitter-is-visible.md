---
title: 'Vorgehensweise: Sicherstellen, dass ein GridSplitter sichtbar ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 0e1984241c07a69e2b350a61dc5873716c6fa5df
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375687"
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
- [Themen zu Vorgehensweisen](gridsplitter-how-to-topics.md)
