---
title: 'Gewusst wie: Hinzufügen eines Wasserzeichens zu einer TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 962d6958de0811863393f930d8672769a50e8265
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550062"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="0a9f9-102">Gewusst wie: Hinzufügen eines Wasserzeichens zu einer TextBox</span><span class="sxs-lookup"><span data-stu-id="0a9f9-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="0a9f9-103">Im folgende Beispiel wird gezeigt, wie die Verwendbarkeit einer <xref:System.Windows.Controls.TextBox> durch Anzeigen eines erläuternden Hintergrundbilds innerhalb eines der <xref:System.Windows.Controls.TextBox> bis der Benutzer Text eingibt, an welchem Punkt das Bild wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="0a9f9-104">Darüber hinaus wird das Hintergrundbild erneut wiederhergestellt werden, wenn der Benutzer die Eingabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="0a9f9-105">Siehe folgende Abbildung.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-105">See illustration below.</span></span>  
  
 <span data-ttu-id="0a9f9-106">![Ein Textfeld mit einem Hintergrundbild](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="0a9f9-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a9f9-107">Der Grund, ein Hintergrundbild wird in diesem Beispiel stattdessen dann einfach bearbeiten verwendet, die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft <xref:System.Windows.Controls.TextBox>, darin, dass ein Hintergrundbild nicht in Konflikt mit dem Datenbindung wird.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a9f9-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a9f9-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0a9f9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a9f9-109">See Also</span></span>  
 [<span data-ttu-id="0a9f9-110">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="0a9f9-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="0a9f9-111">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0a9f9-111">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
