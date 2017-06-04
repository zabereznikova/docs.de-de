---
title: "Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Eingabe, Sicherstellen der Gültigkeit"
  - "MaskedTextBox-Steuerelement [Windows Forms], Überprüfung"
  - "MaskedTextBox-Steuerelement [Windows Forms], Exemplarische Vorgehensweisen"
  - "Text, Steuerelemente für Eingabe"
  - "Benutzereingabe, Steuern"
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement
In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Initialisieren des <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelements  
  
-   Verwenden des <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>\-Ereignishandlers, um den Benutzer zu warnen, wenn ein eingegebenes Zeichen nicht der Maske entspricht  
  
-   Zuweisen eines Typs zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>\-Eigenschaft und Verwenden des <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>\-Ereignishandlers, um den Benutzer zu warnen, wenn der Wert, für den ein Commit ausgeführt wird, für den Typ nicht gültig ist  
  
## Erstellen des Projekts und Hinzufügen eines Steuerelements  
  
#### So fügen Sie dem Formular ein MaskedTextBox\-Steuerelement hinzu  
  
1.  Öffnen Sie das Formular, in dem Sie das <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement platzieren möchten.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement aus der **Toolbox** in das Formular.  
  
3.  Klicken Sie mit der rechten Maustaste auf das Steuerelement, und wählen Sie **Eigenschaften** aus.  Klicken Sie im **Eigenschaftenfenster** auf die **Mask**\-Eigenschaft und dann auf die Schaltfläche mit dem Auslassungszeichen **...** neben dem Eigenschaftennamen.  
  
4.  Wählen Sie im Dialogfeld **Eingabeformat** die Maske **Datum \(Kurzformat\)** aus, und klicken Sie auf **OK**.  
  
5.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A>\-Eigenschaft auf `true` fest.  Durch diese Eigenschaft wird jedes Mal ein kurzer Signalton ausgegeben, wenn der Benutzer ein Zeichen eingibt, das nicht der Maskendefinition entspricht.  
  
 Eine Übersicht der von der Mask\-Eigenschaft unterstützten Zeichen finden Sie in den Hinweisen zur <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft.  
  
## Warnen des Benutzers bei Eingabefehlern  
  
#### Hinzufügen einer QuickInfo\-Sprechblase für abgelehnte Maskeneingaben  
  
1.  Kehren Sie zur **Toolbox** zurück, und fügen Sie dem Formular <xref:System.Windows.Forms.ToolTip> hinzu.  
  
2.  Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>\-Ereignis, durch das <xref:System.Windows.Forms.ToolTip> beim Auftreten eines Eingabefehlers ausgelöst wird.  Die QuickInfo\-Sprechblase bleibt entweder fünf Sekunden oder so lange sichtbar, bis der Benutzer darauf klickt.  
  
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
  
## Warnen des Benutzers bei ungültigen Typen  
  
#### Hinzufügen einer QuickInfo\-Sprechblase für ungültige Datentypen  
  
1.  Weisen Sie im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler des Formulars ein <xref:System.Type>\-Objekt zu, das den <xref:System.DateTime>\-Typ der zum <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement gehörigen <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>\-Eigenschaft darstellt:  
  
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
  
2.  Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>\-Ereignis hinzu:  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.MaskedTextBox>   
 [MaskedTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)