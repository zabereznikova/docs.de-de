---
title: 'Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen'
description: Erfahren Sie, wie Sie Anführungszeichen in einer Text Zeichenfolge platzieren. Außerdem erfahren Sie, wie Sie das Feld "Quote" als Konstante verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 08a3e2ab5662cbbf7825890ab430fddcd7b4a9ce
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903622"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="12a42-104">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="12a42-104">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="12a42-105">Möglicherweise benötigen Sie manchmal Anführungszeichen („ “) in einer Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="12a42-105">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="12a42-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="12a42-106">For example:</span></span>  
  
 <span data-ttu-id="12a42-107">She said, "You deserve a treat!" (Sie sagte: „Du verdienst eine Belohnung!“)</span><span class="sxs-lookup"><span data-stu-id="12a42-107">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="12a42-108">Als Alternative können Sie das <xref:Microsoft.VisualBasic.ControlChars.Quote> Feld auch als Konstante verwenden.</span><span class="sxs-lookup"><span data-stu-id="12a42-108">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="12a42-109">So platzieren Sie Anführungszeichen in einer Zeichenfolge in Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="12a42-109">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="12a42-110">Fügen Sie in Visual Basic zwei Anführungszeichen in eine Zeile als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="12a42-110">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="12a42-111">Fügen Sie in Visual c# und Visual C++ die Escapesequenz \\ "als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="12a42-111">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="12a42-112">Verwenden Sie z.B. folgenden Code, um die oben genannte Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12a42-112">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="12a42-113">Oder</span><span class="sxs-lookup"><span data-stu-id="12a42-113">-or-</span></span>  
  
2. <span data-ttu-id="12a42-114">Fügen Sie das ASCII- oder Unicode-Zeichen für ein Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="12a42-114">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="12a42-115">Verwenden Sie in Visual Basic das ASCII-Zeichen (34).</span><span class="sxs-lookup"><span data-stu-id="12a42-115">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="12a42-116">Verwenden Sie in Visual c# das Unicode-Zeichen (\u0022).</span><span class="sxs-lookup"><span data-stu-id="12a42-116">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="12a42-117">In diesem Beispiel können Sie \u0022 nicht verwenden, da Sie keinen universellen Zeichennamen verwenden dürfen, der ein Zeichen im Basiszeichensatz bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="12a42-117">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="12a42-118">Andernfalls wird C3851 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="12a42-118">Otherwise, you produce C3851.</span></span> <span data-ttu-id="12a42-119">Weitere Informationen finden Sie unter [Compilerfehler C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="12a42-119">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="12a42-120">Oder</span><span class="sxs-lookup"><span data-stu-id="12a42-120">-or-</span></span>  
  
3. <span data-ttu-id="12a42-121">Sie können auch eine Konstante für das Zeichen definieren und bei Bedarf verwenden.</span><span class="sxs-lookup"><span data-stu-id="12a42-121">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12a42-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12a42-122">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="12a42-123">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12a42-123">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="12a42-124">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12a42-124">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="12a42-125">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12a42-125">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="12a42-126">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="12a42-126">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="12a42-127">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12a42-127">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="12a42-128">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12a42-128">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="12a42-129">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12a42-129">TextBox Control</span></span>](textbox-control-windows-forms.md)
