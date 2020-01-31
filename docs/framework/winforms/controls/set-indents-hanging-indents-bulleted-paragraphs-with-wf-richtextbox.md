---
title: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit aufzählen mit dem RichTextBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743017"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a0ca5-102">Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0ca5-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a0ca5-103">Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement verfügt über zahlreiche Optionen, um den angezeigten Text zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="a0ca5-104">Sie können ausgewählte Absätze als aufzählt formatieren, indem Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="a0ca5-105">Sie können auch die Eigenschaften <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>und <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> verwenden, um den Einzug von Absätzen in Bezug auf den linken und rechten Rand des Steuer Elements und den linken Rand anderer Textzeilen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="a0ca5-106">So formatieren Sie einen Absatz als Aufzählung</span><span class="sxs-lookup"><span data-stu-id="a0ca5-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="a0ca5-107">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="a0ca5-108">So ziehen Sie einen Absatz ein</span><span class="sxs-lookup"><span data-stu-id="a0ca5-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="a0ca5-109">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem linken Rand des Steuer Elements und dem linken Rand des Texts in Pixel darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="a0ca5-110">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem linken Rand der ersten Textzeile im Absatz und dem linken Rand der nachfolgenden Zeilen desselben Absatzes in Pixel darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="a0ca5-111">Der Wert der <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>-Eigenschaft gilt nur für Zeilen in einem Absatz, die unter der ersten Zeile umschließt wurden.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="a0ca5-112">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem rechten Rand des Steuer Elements und dem rechten Rand des Texts in Pixel darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a0ca5-113">Alle genannten Eigenschaften wirken sich auf sämtliche Absätze, in denen Text markiert ist, sowie auf nach der aktuellen Einfügemarke eingegebenen Text aus.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="a0ca5-114">Wenn ein Benutzer beispielsweise ein Wort in einem Absatz markiert und dann den Einzug anpasst, wird die neue Einstellung auf den gesamten Absatz, in dem dieses Wort steht, und auf alle Absätze angewendet, die hinter diesem Absatz eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="a0ca5-115">Informationen zum programmgesteuerten auswählen von Text finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0ca5-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ca5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0ca5-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a0ca5-117">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a0ca5-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a0ca5-118">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a0ca5-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
