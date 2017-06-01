---
title: "Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Textes | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Schaltflächentext"
  - "Button-Steuerelement [Windows Forms], Textanzeige"
  - "Schaltflächen, Text"
  - "Beschriftungen, Festlegen"
  - "Beschriftungen, Windows Forms-Steuerelemente"
  - "Steuerelemente [Windows Forms], Beschriftungen"
  - "Beispiele [Windows Forms], Steuerelemente"
  - "Formulare, Beschriftungen"
  - "Bezeichnungen, Hinzufügen zum CommandButton-Steuerelement"
  - "StdFont-Objekt und CommandButton-Beschriftung"
  - "Text"
  - "Text-Eigenschaft, Windows Forms-Steuerelemente"
  - "Text, Windows Forms-Steuerelemente"
  - "Windows Forms, Beschriftungen"
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Textes
Windows Forms\-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt.  Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>\-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist..  Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft festlegen oder zurückgeben.  Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft verwenden.  Sie können den Text aber auch mithilfe des Designers festlegen.   Siehe auch [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente mithilfe des Designers](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes mithilfe des Designers](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Bildes mithilfe des Designers](http://msdn.microsoft.com/library/ms233656\(v=vs.110\))  
  
### So legen Sie den von einem Steuerelement angezeigten Text programmgesteuert fest  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft eine Zeichenfolge fest.  
  
     Wenn Sie eine unterstrichene Zugriffstaste erstellen möchten, setzen Sie ein kaufmännisches Und\-Zeichen \(&\) vor den Buchstaben der Zugriffstaste.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp#  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente.  Mit der folgenden Codezeile wird der Text des Menüelements beispielsweise wie folgt festgelegt: "& Now For Something Completely Different":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp#  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=fullName>   
 [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)