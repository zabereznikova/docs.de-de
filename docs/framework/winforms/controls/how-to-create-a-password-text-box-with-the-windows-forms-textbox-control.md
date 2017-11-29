---
title: "Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: caf5cef9e23134715101545902e32e72d63c0aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="d3ff2-102">Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ff2-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="d3ff2-103">Ein Kennwortfeld ist ein Windows Forms-Textfeld, in dem Platzhalterzeichen angezeigt, während ein Benutzer, eine Zeichenfolge eingibt.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="d3ff2-104">So erstellen das Textfeld "Kennwort"</span><span class="sxs-lookup"><span data-stu-id="d3ff2-104">To create a password text box</span></span>  
  
1.  <span data-ttu-id="d3ff2-105">Festlegen der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft von der <xref:System.Windows.Forms.TextBox> Steuerelement auf ein bestimmtes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="d3ff2-106">Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen im Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="d3ff2-107">Geben Sie z. B. wenn Sternchen im Kennwortfeld angezeigt werden sollen, * für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-107">For example, if you want asterisks displayed in the password box, specify * for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="d3ff2-108">Unabhängig davon, welche Zeichen, die ein Benutzer in das Textfeld eingibt, wird anschließend ein Sternchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2.  <span data-ttu-id="d3ff2-109">(Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="d3ff2-110">Die Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="d3ff2-111">Wenn die maximale Länge überschritten wird, das System gibt einen Signalton aus, und das Textfeld akzeptiert keine weiteren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="d3ff2-112">Beachten Sie, dass Sie nicht dazu, wie die maximale Länge von Kennwörtern mithilfe Hacker, die versuchen werden kann, das Kennwort erraten möchten.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="d3ff2-113">Im folgenden Codebeispiel wird gezeigt, wie ein Textfeld, das initialisiert werden, die akzeptiert einer Zeichenfolge bis zu 14 Zeichen lang sein und Sternchen anstelle der Zeichenfolge angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="d3ff2-114">Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt; es muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d3ff2-115">Mithilfe der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen das Kennwort eines Benutzers zu bestimmen, ob sie die Beobachtung.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="d3ff2-116">Durch diese Sicherheitsmaßnahme deckt keine Art von Speicher oder die Übertragung des Kennworts, die aufgrund Ihrer Anwendungslogik auftreten können.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="d3ff2-117">Da der eingegebene Text nicht in keiner Weise verschlüsselt ist, sollten Sie sie behandeln, wie alle anderen vertraulichen Daten.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="d3ff2-118">Obwohl es nicht als solche angezeigt wird, wird das Kennwort (es sei denn, Sie einige zusätzliche Sicherheitsmaßnahme implementiert haben) immer noch als nur-Text-Zeichenfolge behandelt.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d3ff2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3ff2-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="d3ff2-120">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d3ff2-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="d3ff2-121">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ff2-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d3ff2-122">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="d3ff2-122">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="d3ff2-123">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d3ff2-123">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="d3ff2-124">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ff2-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d3ff2-125">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ff2-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d3ff2-126">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d3ff2-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
