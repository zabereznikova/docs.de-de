---
title: Programmgesteuertes Ändern der Auswahl in einem RichTextBox-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096224"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="c1756-102">Programmgesteuertes Ändern der Auswahl in einem RichTextBox-Element</span><span class="sxs-lookup"><span data-stu-id="c1756-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="c1756-103">Dieses Beispiel zeigt, wie Sie programmgesteuert ändern Sie die aktuelle Auswahl in einem <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="c1756-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="c1756-104">Diese Auswahl ist identisch, als ob der Benutzer den Inhalt mithilfe der Benutzeroberfläche ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c1756-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1756-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1756-105">Example</span></span>  
 <span data-ttu-id="c1756-106">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> -Steuerelement mit einfachem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c1756-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c1756-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1756-107">Example</span></span>  
 <span data-ttu-id="c1756-108">Der folgende Code wählt programmgesteuert beliebigen Text, klickt der Benutzer innerhalb der <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="c1756-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c1756-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1756-109">See also</span></span>

- [<span data-ttu-id="c1756-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c1756-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="c1756-111">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="c1756-111">TextBox Overview</span></span>](textbox-overview.md)
