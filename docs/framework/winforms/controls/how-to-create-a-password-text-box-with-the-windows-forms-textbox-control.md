---
title: 'Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: b6fe0e615cc5bbd0f549505ed9e6add8d7a51433
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523986"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="3f4f3-102">Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f4f3-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="3f4f3-103">Ein Kennwortfeld ist ein Windows Forms-Textfeld ein, die Platzhalterzeichen zeigt an, wenn ein Benutzer eine Zeichenfolge eingibt.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="3f4f3-104">Erstellen Sie ein Kennwort-Textfeld</span><span class="sxs-lookup"><span data-stu-id="3f4f3-104">To create a password text box</span></span>  
  
1.  <span data-ttu-id="3f4f3-105">Legen Sie die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft der <xref:System.Windows.Forms.TextBox> Steuerelement auf ein bestimmtes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="3f4f3-106">Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen, die Sie im Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="3f4f3-107">Wenn Sternchen im Kennwortfeld angezeigt werden sollen, z. B. Geben Sie \* für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="3f4f3-108">Unabhängig davon, welche Zeichen, die ein Benutzer in das Textfeld eingibt, wird dann ein Sternchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2.  <span data-ttu-id="3f4f3-109">(Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="3f4f3-110">Die Eigenschaft wird bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="3f4f3-111">Wenn die maximale Länge überschritten wird, wird das System gibt einen Signalton aus, und im Textfeld akzeptiert keine weiteren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="3f4f3-112">Beachten Sie, dass Sie nicht dazu, wie die maximale Länge eines Kennworts für Hacker sein kann, die das Kennwort zu erraten versuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="3f4f3-113">Im folgenden Codebeispiel wird veranschaulicht, ein Textfeld zu initialisieren, der akzeptiert einer Zeichenfolge mit bis zu 14 Zeichen lang sein und durch Sternchen anstelle der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="3f4f3-114">Die `InitializeMyControl` -Prozedur wird nicht automatisch ausgeführt; muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3f4f3-115">Mithilfe der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen nicht das Kennwort eines Benutzers zu bestimmen, wenn sie die Beobachtung.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="3f4f3-116">Durch diese Sicherheitsmaßnahme deckt keine Art von gespeichert oder übertragen des Kennworts, die aufgrund Ihrer Anwendungslogik auftreten können.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="3f4f3-117">Da der eingegebene Text in keiner Weise nicht verschlüsselt ist, sollten Sie sie behandeln, wie alle anderen vertraulichen Daten.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="3f4f3-118">Obwohl es nicht als solche angezeigt wird, wird das Kennwort (es sei denn, Sie einige zusätzliche Sicherheitsmaßnahme implementiert haben) immer noch als nur-Text-Zeichenfolge behandelt.</span><span class="sxs-lookup"><span data-stu-id="3f4f3-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f4f3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f4f3-119">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="3f4f3-120">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3f4f3-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="3f4f3-121">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f4f3-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="3f4f3-122">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="3f4f3-122">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="3f4f3-123">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3f4f3-123">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="3f4f3-124">Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f4f3-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3f4f3-125">Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an</span><span class="sxs-lookup"><span data-stu-id="3f4f3-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3f4f3-126">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3f4f3-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
