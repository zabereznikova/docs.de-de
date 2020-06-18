---
title: Textfeld "Kennwort" mit TextBox-Steuerelement erstellen
description: Erfahren Sie, wie Sie einen Windows Forms Text, in dem Platzhalter Zeichen angezeigt werden, bei der typeinfügezeichen-Zeichenfolge.
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
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904311"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="95802-103">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95802-103">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="95802-104">Ein Kennwortfeld ist ein Windows Forms Textfeld, in dem Platzhalter Zeichen angezeigt werden, während ein Benutzer eine Zeichenfolge eingibt.</span><span class="sxs-lookup"><span data-stu-id="95802-104">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="95802-105">So erstellen Sie ein Kennwort-Textfeld</span><span class="sxs-lookup"><span data-stu-id="95802-105">To create a password text box</span></span>

1. <span data-ttu-id="95802-106">Legen Sie die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft des- <xref:System.Windows.Forms.TextBox> Steuer Elements auf ein bestimmtes Zeichen fest.</span><span class="sxs-lookup"><span data-stu-id="95802-106">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="95802-107">Die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen an, das im Textfeld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="95802-107">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="95802-108">Wenn Sie z. b. Sternchen im Feld Kennwort anzeigen möchten, geben Sie für die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster \* an.</span><span class="sxs-lookup"><span data-stu-id="95802-108">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="95802-109">Unabhängig davon, welches Zeichen ein Benutzer im Textfeld eingibt, wird ein Sternchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95802-109">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="95802-110">Optionale Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="95802-110">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="95802-111">Die-Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="95802-111">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="95802-112">Wenn die maximale Länge überschritten wird, gibt das System ein Signal aus, und das Textfeld akzeptiert keine weiteren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="95802-112">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="95802-113">Beachten Sie, dass Sie dies möglicherweise nicht tun möchten, da die maximale Länge eines Kennworts für Hacker verwendet werden kann, die versuchen, das Kennwort zu erraten.</span><span class="sxs-lookup"><span data-stu-id="95802-113">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="95802-114">Im folgenden Codebeispiel wird veranschaulicht, wie ein Textfeld initialisiert wird, das eine Zeichenfolge mit einer Länge von bis zu 14 Zeichen akzeptiert und Sternchen anstelle der Zeichenfolge anzeigt.</span><span class="sxs-lookup"><span data-stu-id="95802-114">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="95802-115">Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt. Sie muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="95802-115">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="95802-116">Mithilfe der- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen das Kennwort eines Benutzers nicht ermitteln können, wenn der Benutzer die Eingabe des Benutzers eingibt.</span><span class="sxs-lookup"><span data-stu-id="95802-116">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="95802-117">Diese Sicherheitsmaßnahme deckt keinerlei Speicherung oder Übertragung des Kennworts ab, das aufgrund ihrer Anwendungslogik auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="95802-117">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="95802-118">Da der eingegebene Text in keiner Weise verschlüsselt ist, sollten Sie ihn wie alle anderen vertraulichen Daten behandeln.</span><span class="sxs-lookup"><span data-stu-id="95802-118">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="95802-119">Obwohl es nicht als solches erscheint, wird das Kennwort immer noch als nur-Text-Zeichenfolge behandelt (es sei denn, Sie haben eine zusätzliche Sicherheitsmaßnahme implementiert).</span><span class="sxs-lookup"><span data-stu-id="95802-119">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="95802-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95802-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="95802-121">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="95802-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="95802-122">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95802-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="95802-123">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="95802-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="95802-124">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="95802-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="95802-125">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95802-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="95802-126">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95802-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="95802-127">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="95802-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
