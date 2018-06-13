---
title: 'Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem "TextBox"-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 79ecf1d5dccee0dacef8e288c0c2e044334e65d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556031"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="46c9b-102">Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem "TextBox"-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="46c9b-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="46c9b-103">In diesem Beispiel wird gezeigt, wie zur Positionierung des Cursors am Anfang oder Ende des Textinhalts einer <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="46c9b-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46c9b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46c9b-104">Example</span></span>  
 <span data-ttu-id="46c9b-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt eine <xref:System.Windows.Controls.TextBox> steuern und weist ihr einen Namen.</span><span class="sxs-lookup"><span data-stu-id="46c9b-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="46c9b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46c9b-106">Example</span></span>  
 <span data-ttu-id="46c9b-107">Zur Positionierung des Cursors am Anfang des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode, und geben Sie die Auswahl Position 0 und Auswahllänge 0 starten.</span><span class="sxs-lookup"><span data-stu-id="46c9b-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="46c9b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46c9b-108">Example</span></span>  
 <span data-ttu-id="46c9b-109">Zur Positionierung des Cursors am Ende des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode, und geben Sie die Auswahl Startposition an, der die Länge des Textinhalts 0 gleich.</span><span class="sxs-lookup"><span data-stu-id="46c9b-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="46c9b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46c9b-110">See Also</span></span>  
 [<span data-ttu-id="46c9b-111">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="46c9b-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="46c9b-112">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="46c9b-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
