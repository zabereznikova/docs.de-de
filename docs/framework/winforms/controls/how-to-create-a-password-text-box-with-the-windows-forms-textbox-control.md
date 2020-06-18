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
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms

Ein Kennwortfeld ist ein Windows Forms Textfeld, in dem Platzhalter Zeichen angezeigt werden, während ein Benutzer eine Zeichenfolge eingibt.

### <a name="to-create-a-password-text-box"></a>So erstellen Sie ein Kennwort-Textfeld

1. Legen Sie die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft des- <xref:System.Windows.Forms.TextBox> Steuer Elements auf ein bestimmtes Zeichen fest.

    Die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen an, das im Textfeld angezeigt wird. Wenn Sie z. b. Sternchen im Feld Kennwort anzeigen möchten, geben Sie für die- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster * an. Unabhängig davon, welches Zeichen ein Benutzer im Textfeld eingibt, wird ein Sternchen angezeigt.

2. Optionale Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft fest. Die-Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können. Wenn die maximale Länge überschritten wird, gibt das System ein Signal aus, und das Textfeld akzeptiert keine weiteren Zeichen. Beachten Sie, dass Sie dies möglicherweise nicht tun möchten, da die maximale Länge eines Kennworts für Hacker verwendet werden kann, die versuchen, das Kennwort zu erraten.

    Im folgenden Codebeispiel wird veranschaulicht, wie ein Textfeld initialisiert wird, das eine Zeichenfolge mit einer Länge von bis zu 14 Zeichen akzeptiert und Sternchen anstelle der Zeichenfolge anzeigt. Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt. Sie muss aufgerufen werden.

    > [!IMPORTANT]
    > Mithilfe der- <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen das Kennwort eines Benutzers nicht ermitteln können, wenn der Benutzer die Eingabe des Benutzers eingibt. Diese Sicherheitsmaßnahme deckt keinerlei Speicherung oder Übertragung des Kennworts ab, das aufgrund ihrer Anwendungslogik auftreten kann. Da der eingegebene Text in keiner Weise verschlüsselt ist, sollten Sie ihn wie alle anderen vertraulichen Daten behandeln. Obwohl es nicht als solches erscheint, wird das Kennwort immer noch als nur-Text-Zeichenfolge behandelt (es sei denn, Sie haben eine zusätzliche Sicherheitsmaßnahme implementiert).

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
