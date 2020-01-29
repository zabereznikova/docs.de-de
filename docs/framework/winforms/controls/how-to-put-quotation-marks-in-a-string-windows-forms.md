---
title: 'Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen'
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
ms.openlocfilehash: c14747291d6c41144eef97b258f852bbe14ef07d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735900"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="662b7-102">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="662b7-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="662b7-103">Möglicherweise benötigen Sie manchmal Anführungszeichen („ “) in einer Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="662b7-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="662b7-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="662b7-104">For example:</span></span>  
  
 <span data-ttu-id="662b7-105">She said, "You deserve a treat!" (Sie sagte: „Du verdienst eine Belohnung!“)</span><span class="sxs-lookup"><span data-stu-id="662b7-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="662b7-106">Als Alternative können Sie auch das <xref:Microsoft.VisualBasic.ControlChars.Quote>-Feld als Konstante verwenden.</span><span class="sxs-lookup"><span data-stu-id="662b7-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="662b7-107">So platzieren Sie Anführungszeichen in einer Zeichenfolge in Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="662b7-107">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="662b7-108">Fügen Sie in Visual Basic zwei Anführungszeichen in eine Zeile als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="662b7-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="662b7-109">Fügen Sie C# die Escapesequenz in Visual und Visual C++\\"als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="662b7-109">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="662b7-110">Verwenden Sie z.B. folgenden Code, um die oben genannte Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="662b7-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="662b7-111">\- oder -</span><span class="sxs-lookup"><span data-stu-id="662b7-111">-or-</span></span>  
  
2. <span data-ttu-id="662b7-112">Fügen Sie das ASCII- oder Unicode-Zeichen für ein Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="662b7-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="662b7-113">Verwenden Sie in Visual Basic das ASCII-Zeichen (34).</span><span class="sxs-lookup"><span data-stu-id="662b7-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="662b7-114">Verwenden Sie C#in Visual das Unicode-Zeichen (\u0022).</span><span class="sxs-lookup"><span data-stu-id="662b7-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    > <span data-ttu-id="662b7-115">In diesem Beispiel können Sie \u0022 nicht verwenden, da Sie keinen universellen Zeichennamen verwenden dürfen, der ein Zeichen im Basiszeichensatz bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="662b7-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="662b7-116">Andernfalls wird C3851 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="662b7-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="662b7-117">Weitere Informationen finden Sie unter [Compilerfehler C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="662b7-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="662b7-118">\- oder -</span><span class="sxs-lookup"><span data-stu-id="662b7-118">-or-</span></span>  
  
3. <span data-ttu-id="662b7-119">Sie können auch eine Konstante für das Zeichen definieren und bei Bedarf verwenden.</span><span class="sxs-lookup"><span data-stu-id="662b7-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="662b7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="662b7-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="662b7-121">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="662b7-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="662b7-122">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="662b7-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="662b7-123">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="662b7-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="662b7-124">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="662b7-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="662b7-125">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="662b7-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="662b7-126">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="662b7-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="662b7-127">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="662b7-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
