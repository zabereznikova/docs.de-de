---
title: "Gewusst wie: Setzen von Anf&#252;hrungszeichen in Zeichenfolgen (Windows&#160;Forms) | Microsoft Docs"
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
  - "Anführungszeichen"
  - "Anführungszeichen, Hinzufügen zu Zeichenfolgen in Textfeldern"
  - "TextBox-Steuerelement [Windows Forms], Anzeigen von Anführungszeichen"
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Setzen von Anf&#252;hrungszeichen in Zeichenfolgen (Windows&#160;Forms)
Gelegentlich kommt es vor, dass Sie Anführungszeichen \(""\) in eine Textzeichenfolge einfügen möchten.  Beispiele:  
  
 She said, "You deserve a treat\!"  
  
 Wahlweise können Sie das <xref:Microsoft.VisualBasic.ControlChars.Quote>\-Feld auch als Konstante verwenden.  
  
### So fügen Sie Anführungszeichen in eine Codezeichenfolge ein  
  
1.  Fügen Sie in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] zwei Anführungszeichen in einer Zeile als eingebettetes Anführungszeichen ein.  Fügen Sie in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] die Escapesequenz \\" als eingebettetes Anführungszeichen ein.  Die oben aufgeführte Zeichenfolge generieren Sie beispielsweise mit dem folgenden Code.  
  
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
  
     \- oder \-  
  
2.  Fügen Sie das entsprechende ASCII\- oder Unicode\-Zeichen für ein Anführungszeichen ein.  Verwenden Sie in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] das ASCII\-Zeichen \(34\).  Verwenden Sie in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] das Unicode\-Zeichen \(\\u0022\).  
  
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
    >  In diesem Beispiel ist die Verwendung von \\u0022 nicht möglich, da Sie keinen universellen Zeichennamen verwenden können, der ein Zeichen im Basiszeichensatz kennzeichnet.  Andernfalls wird der Fehler C3851 ausgegeben.  Weitere Informationen hierzu finden Sie unter [Compilerfehler C3851](../Topic/Compiler%20Error%20C3851.md).  
  
     \- oder \-  
  
3.  Darüber hinaus kann auch eine Konstante für das Zeichen definiert und bei Bedarf verwendet werden.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 <xref:Microsoft.VisualBasic.ControlChars.Quote>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)