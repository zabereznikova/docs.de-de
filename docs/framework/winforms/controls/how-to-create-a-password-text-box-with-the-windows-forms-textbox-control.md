---
title: Textfeld "Kennwort" mit TextBox-Steuerelement erstellen
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
ms.openlocfilehash: ff4706a736d15f14cf437c808219e9088773dc6d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731280"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="cecfa-102">Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cecfa-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="cecfa-103">Ein Kennwortfeld ist ein Windows Forms Textfeld, in dem Platzhalter Zeichen angezeigt werden, während ein Benutzer eine Zeichenfolge eingibt.</span><span class="sxs-lookup"><span data-stu-id="cecfa-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="cecfa-104">So erstellen Sie ein Kennwort-Textfeld</span><span class="sxs-lookup"><span data-stu-id="cecfa-104">To create a password text box</span></span>

1. <span data-ttu-id="cecfa-105">Legen Sie die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox>-Steuer Elements auf ein bestimmtes Zeichen fest.</span><span class="sxs-lookup"><span data-stu-id="cecfa-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="cecfa-106">Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>-Eigenschaft gibt das Zeichen an, das im Textfeld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cecfa-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="cecfa-107">Wenn Sie z. b. Sternchen im Feld Kennwort anzeigen möchten, geben Sie \* für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>-Eigenschaft in der Eigenschaftenfenster an.</span><span class="sxs-lookup"><span data-stu-id="cecfa-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="cecfa-108">Unabhängig davon, welches Zeichen ein Benutzer im Textfeld eingibt, wird ein Sternchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cecfa-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="cecfa-109">Optionale Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="cecfa-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="cecfa-110">Die-Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="cecfa-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="cecfa-111">Wenn die maximale Länge überschritten wird, gibt das System ein Signal aus, und das Textfeld akzeptiert keine weiteren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cecfa-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="cecfa-112">Beachten Sie, dass Sie dies möglicherweise nicht tun möchten, da die maximale Länge eines Kennworts für Hacker verwendet werden kann, die versuchen, das Kennwort zu erraten.</span><span class="sxs-lookup"><span data-stu-id="cecfa-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="cecfa-113">Im folgenden Codebeispiel wird veranschaulicht, wie ein Textfeld initialisiert wird, das eine Zeichenfolge mit einer Länge von bis zu 14 Zeichen akzeptiert und Sternchen anstelle der Zeichenfolge anzeigt.</span><span class="sxs-lookup"><span data-stu-id="cecfa-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="cecfa-114">Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt. Es muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cecfa-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cecfa-115">Mithilfe der Eigenschaft <xref:System.Windows.Forms.TextBox.PasswordChar%2A> in einem Textfeld können Sie sicherstellen, dass andere Personen das Kennwort eines Benutzers nicht ermitteln können, wenn der Benutzer die Eingabe des Benutzers eingibt.</span><span class="sxs-lookup"><span data-stu-id="cecfa-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="cecfa-116">Diese Sicherheitsmaßnahme deckt keinerlei Speicherung oder Übertragung des Kennworts ab, das aufgrund ihrer Anwendungslogik auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="cecfa-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="cecfa-117">Da der eingegebene Text in keiner Weise verschlüsselt ist, sollten Sie ihn wie alle anderen vertraulichen Daten behandeln.</span><span class="sxs-lookup"><span data-stu-id="cecfa-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="cecfa-118">Obwohl es nicht als solches erscheint, wird das Kennwort immer noch als nur-Text-Zeichenfolge behandelt (es sei denn, Sie haben eine zusätzliche Sicherheitsmaßnahme implementiert).</span><span class="sxs-lookup"><span data-stu-id="cecfa-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cecfa-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cecfa-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="cecfa-120">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cecfa-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="cecfa-121">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cecfa-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="cecfa-122">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="cecfa-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="cecfa-123">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="cecfa-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="cecfa-124">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cecfa-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cecfa-125">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cecfa-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cecfa-126">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cecfa-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
