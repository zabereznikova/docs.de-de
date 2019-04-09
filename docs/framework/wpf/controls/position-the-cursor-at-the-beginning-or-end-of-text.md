---
title: 'Vorgehensweise: Positionieren des Cursors am Anfang oder Ende von Text in einem TextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 3d7da5daf09e06938b8366e0f5f98a599cae4571
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186224"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="4dd6b-102">Vorgehensweise: Positionieren des Cursors am Anfang oder Ende von Text in einem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4dd6b-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="4dd6b-103">In diesem Beispiel wird gezeigt, wie zur Positionierung des Cursors am Anfang oder Ende des Text-Inhalt, der eine <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dd6b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dd6b-104">Example</span></span>  
 <span data-ttu-id="4dd6b-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt eine <xref:System.Windows.Controls.TextBox> steuern und weist ihr einen Namen.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="4dd6b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dd6b-106">Example</span></span>  
 <span data-ttu-id="4dd6b-107">Zur Positionierung des Cursors am Anfang des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode, und geben Sie die Auswahl Startposition 0 sowie eine Auswahllänge von 0 starten.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="4dd6b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dd6b-108">Example</span></span>  
 <span data-ttu-id="4dd6b-109">Zur Positionierung des Cursors am Ende des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode, und geben Sie die Startposition der Bereichsauswahl gleich der Länge des Textinhalts und eine Auswahllänge von 0.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="4dd6b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dd6b-110">See also</span></span>

- [<span data-ttu-id="4dd6b-111">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="4dd6b-111">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="4dd6b-112">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4dd6b-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
