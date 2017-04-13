---
title: "Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Kennwortfelder, Erstellen"
  - "PasswordChar-Eigenschaft in Textfeldern"
  - "Kennwörter, Eingabeformat"
  - "Kennwörter, Kennworttextfeld"
  - "TextBox-Steuerelement [Windows Forms], Eingeben von Kennwörtern"
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows&#160;Forms
Bei einem Kennwortfeld handelt es sich um ein Windows Forms\-Textfeld, in dem Platzhalterzeichen generiert werden, während der Benutzer eine Zeichenfolge eingibt.  
  
### So erstellen Sie ein Kennwort\-Textfeld  
  
1.  Legen Sie für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>\-Eigenschaft des <xref:System.Windows.Forms.TextBox>\-Steuerelements ein bestimmtes Zeichen fest.  
  
     Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>\-Eigenschaft bestimmt, welches Zeichen im Textfeld angezeigt wird.  Wenn im Kennwortfeld beispielsweise Sternchen angezeigt werden sollen, geben Sie im Eigenschaftenfenster für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A>\-Eigenschaft ein Sternchen \(\*\) an.  Daraufhin wird im Textfeld ein Sternchen angezeigt, unabhängig davon, welches Zeichen der Benutzer eingibt.  
  
2.  \(Optional\) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>\-Eigenschaft fest.  Diese Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können.  Sobald die maximale Länge überschritten wird, gibt das System einen Signalton aus, und das Textfeld nimmt keine weiteren Zeichen mehr auf.  Beachten Sie, dass es Hackern durch die Kenntnis der maximalen Länge des Kennworts möglicherweise erleichtert wird, das Kennwort zu erraten.  
  
     Durch das folgende Codebeispiel wird die Initialisierung eines Textfelds veranschaulicht, in das eine Zeichenfolge mit maximal 14 Zeichen eingegeben werden kann, die durch Sternchen ersetzt werden.  Die`InitializeMyControl`Prozedur führt nicht automatisch aus. Sie muss aufgerufen werden.  
  
    > [!IMPORTANT]
    >  Mithilfe der <xref:System.Windows.Forms.TextBox.PasswordChar%2A>\-Eigenschaft für ein Textfeld können Sie verhindern, dass andere Personen das Kennwort eines Benutzers herausfinden, wenn Sie ihn bei der Eingabe beobachten.  Diese Sicherheitsmaßnahme verhindert nicht alle Möglichkeiten zum Speichern oder zur Übermittlung des Kennworts aufgrund der Anwendungslogik.  Da der eingegebene Text völlig unverschlüsselt ist, muss er wie alle anderen vertraulichen Daten behandelt werden.  Auch wenn das Kennwort nicht als Volltextzeichenfolge angezeigt wird, wird es als solche behandelt \(sofern Sie keine zusätzlichen Sicherheitsmaßnahmen implementiert haben\).  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)