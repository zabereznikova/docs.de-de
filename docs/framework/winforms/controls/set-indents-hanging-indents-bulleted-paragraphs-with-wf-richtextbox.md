---
title: 'Vorgehensweise: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: ef579923ac2b9ea9905a60000d93f6bfc90ed5b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903018"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="8d436-102">Vorgehensweise: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d436-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="8d436-103">Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Optionen zum Formatieren des Texts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d436-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="8d436-104">Sie können markierte Absätze als Aufzählungen formatieren, durch Festlegen der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d436-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="8d436-105">Sie können auch die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, und <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaften den Einzug der Absätze relativ zum linken und rechten Rand des Steuerelements und dem linken Rand anderer Textzeilen festlegen.</span><span class="sxs-lookup"><span data-stu-id="8d436-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="8d436-106">So formatieren Sie einen Absatz als Aufzählung</span><span class="sxs-lookup"><span data-stu-id="8d436-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="8d436-107">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="8d436-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="8d436-108">So ziehen Sie einen Absatz ein</span><span class="sxs-lookup"><span data-stu-id="8d436-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="8d436-109">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem linken Rand des Steuerelements und dem linken Rand des Texts in Pixel.</span><span class="sxs-lookup"><span data-stu-id="8d436-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="8d436-110">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem linken Rand der ersten Zeile des Texts im Absatz und dem linken Rand nachfolgender Zeilen in demselben Absatz in Pixel.</span><span class="sxs-lookup"><span data-stu-id="8d436-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="8d436-111">Der Wert des der <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaft gilt nur für Zeilen in einem Absatz, die der ersten Zeile umschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="8d436-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="8d436-112">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem rechten Rand des Steuerelements und dem rechten Rand des Texts in Pixel.</span><span class="sxs-lookup"><span data-stu-id="8d436-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
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
    >  <span data-ttu-id="8d436-113">Alle genannten Eigenschaften wirken sich auf sämtliche Absätze, in denen Text markiert ist, sowie auf nach der aktuellen Einfügemarke eingegebenen Text aus.</span><span class="sxs-lookup"><span data-stu-id="8d436-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="8d436-114">Wenn ein Benutzer beispielsweise ein Wort in einem Absatz markiert und dann den Einzug anpasst, wird die neue Einstellung auf den gesamten Absatz, in dem dieses Wort steht, und auf alle Absätze angewendet, die hinter diesem Absatz eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8d436-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="8d436-115">Informationen zum Auswählen von Text programmgesteuert, finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d436-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d436-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d436-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="8d436-117">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8d436-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="8d436-118">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="8d436-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
