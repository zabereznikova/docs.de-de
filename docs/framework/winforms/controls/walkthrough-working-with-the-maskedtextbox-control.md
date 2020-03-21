---
title: 'Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182059"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement
In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Initialisieren <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements  
  
- Verwenden <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> des Ereignishandlers, um den Benutzer zu warnen, wenn ein Zeichen nicht mit der Maske übereinstimmt  
  
- Zuweisen eines Typs <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> zur Eigenschaft <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> und Verwenden des Ereignishandlers zum Warnen des Benutzers, wenn der Wert, den er zu übertragen versucht, für den Typ ungültig ist  
  
## <a name="creating-the-project-and-adding-a-control"></a>Erstellen des Projekts und Hinzufügen eines Steuerelements  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>So fügen Sie dem Formular ein MaskedTextBox-Steuerelement hinzu  
  
1. Öffnen Sie das Formular, in <xref:System.Windows.Forms.MaskedTextBox> dem Sie das Steuerelement platzieren möchten.  
  
2. Ziehen <xref:System.Windows.Forms.MaskedTextBox> Sie ein Steuerelement aus der **Toolbox** in das Formular.  
  
3. Klicken Sie mit der rechten Maustaste auf das Steuerelement, und wählen Sie **Eigenschaften**aus. Wählen Sie im **Eigenschaftenfenster** die **Mask-Eigenschaft** aus, und klicken Sie auf die Schaltfläche **...** (Auslassungspunkte) neben dem Eigenschaftsnamen.  
  
4. Wählen Sie im Dialogfeld **Eingabemaske** die **Kurzdatumsmaske** aus, und klicken Sie auf **OK**.  
  
5. Legen Sie im <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> **Eigenschaftenfenster** die Eigenschaft auf fest. `true` Diese Eigenschaft bewirkt, dass jedes Mal, wenn der Benutzer versucht, ein Zeichen einzugeben, das gegen die Maskendefinition verstößt, ein kurzer Signalton ertönt.  
  
 Eine Zusammenfassung der Zeichen, die von der Mask-Eigenschaft <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> unterstützt werden, finden Sie im Abschnitt "Bemerkungen" der Eigenschaft.  
  
## <a name="alert-the-user-to-input-errors"></a>Warnung des Benutzers vor Eingabefehlern  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Hinzufügen einer Sprechblasenspitze für abgelehnte Maskeneingabe  
  
1. Kehren Sie zur Toolbox <xref:System.Windows.Forms.ToolTip> **zurück,** und fügen Sie dem Formular eine hinzu.  
  
2. Erstellen Sie einen <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> Ereignishandler für <xref:System.Windows.Forms.ToolTip> das Ereignis, das den Zeitpunkt auslöst, an dem ein Eingabefehler auftritt. Die Ballonspitze bleibt fünf Sekunden lang sichtbar, oder bis der Benutzer darauf klickt.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Warnung des Benutzers auf einen ungültigen Typ  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Hinzufügen einer Sprechblasenspitze für ungültige Datentypen  
  
1. Weisen Sie im <xref:System.Windows.Forms.Form.Load> Ereignishandler des <xref:System.Type> Formulars <xref:System.DateTime> der <xref:System.Windows.Forms.MaskedTextBox> Eigenschaft des <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> Steuerelements ein Objekt zu, das den Typ darstellt:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>-Ereignis hinzu:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MaskedTextBox>
- [MaskedTextBox-Steuerelement](maskedtextbox-control-windows-forms.md)
