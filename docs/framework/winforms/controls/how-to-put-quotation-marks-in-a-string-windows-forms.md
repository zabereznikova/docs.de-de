---
title: 'Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)'
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
ms.openlocfilehash: 0148f9fde9d69bb1605776f1ab617079be96b59e
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053463"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="64b38-102">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="64b38-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="64b38-103">Möglicherweise benötigen Sie manchmal Anführungszeichen („ “) in einer Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="64b38-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="64b38-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="64b38-104">For example:</span></span>  
  
 <span data-ttu-id="64b38-105">She said, "You deserve a treat!" (Sie sagte: „Du verdienst eine Belohnung!“)</span><span class="sxs-lookup"><span data-stu-id="64b38-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="64b38-106">Als Alternative können Sie auch die <xref:Microsoft.VisualBasic.ControlChars.Quote> Feld als Konstante.</span><span class="sxs-lookup"><span data-stu-id="64b38-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="64b38-107">So platzieren Sie Anführungszeichen in einer Zeichenfolge in Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="64b38-107">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="64b38-108">Fügen Sie in Visual Basic zwei Anführungszeichen in einer Zeile als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="64b38-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="64b38-109">In visuellen C# und visuelle C++, fügen Sie die Escape-Sequenz \\"als eingebettetes Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="64b38-109">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="64b38-110">Verwenden Sie z.B. folgenden Code, um die oben genannte Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64b38-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="64b38-111">- oder - </span><span class="sxs-lookup"><span data-stu-id="64b38-111">-or-</span></span>  
  
2. <span data-ttu-id="64b38-112">Fügen Sie das ASCII- oder Unicode-Zeichen für ein Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="64b38-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="64b38-113">Verwenden Sie in Visual Basic das ASCII-Zeichen (34).</span><span class="sxs-lookup"><span data-stu-id="64b38-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="64b38-114">In visuellen C#, verwenden Sie das Unicode-Zeichen (\u0022).</span><span class="sxs-lookup"><span data-stu-id="64b38-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    >  <span data-ttu-id="64b38-115">In diesem Beispiel können Sie \u0022 nicht verwenden, da Sie keinen universellen Zeichennamen verwenden dürfen, der ein Zeichen im Basiszeichensatz bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="64b38-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="64b38-116">Andernfalls wird C3851 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="64b38-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="64b38-117">Weitere Informationen finden Sie unter [Compilerfehler C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="64b38-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="64b38-118">- oder - </span><span class="sxs-lookup"><span data-stu-id="64b38-118">-or-</span></span>  
  
3. <span data-ttu-id="64b38-119">Sie können auch eine Konstante für das Zeichen definieren und bei Bedarf verwenden.</span><span class="sxs-lookup"><span data-stu-id="64b38-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64b38-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64b38-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="64b38-121">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64b38-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="64b38-122">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64b38-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="64b38-123">Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64b38-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="64b38-124">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="64b38-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="64b38-125">Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64b38-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="64b38-126">Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an</span><span class="sxs-lookup"><span data-stu-id="64b38-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="64b38-127">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64b38-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
