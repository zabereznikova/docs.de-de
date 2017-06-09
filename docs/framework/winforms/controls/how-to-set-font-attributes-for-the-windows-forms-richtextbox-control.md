---
title: "Gewusst wie: Festlegen von Schriftartattributen f&#252;r das RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - ".rtf-Dateien, Formatieren im RichTextBox-Steuerelement"
  - "Schriftarten, Ändern von Attributen im RichTextBox-Steuerelement"
  - "Formatieren [Windows Forms]"
  - "RichTextBox-Steuerelement [Windows Forms], Festlegen von Schriftattributen"
  - "RTF-Dateien, Formatieren im RichTextBox-Steuerelement"
  - "Text [Windows Forms]"
  - "Textfelder, Formatieren von Text"
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Festlegen von Schriftartattributen f&#252;r das RichTextBox-Steuerelement von Windows&#160;Forms
Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms stellt zahlreiche Formatierungsoptionen für den in ihm angezeigten Text bereit.  Mithilfe der <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>\-Eigenschaft können die markierten Zeichen fett, unterstrichen oder kursiv formatiert werden.  Sie können mit dieser Eigenschaft außerdem die Größe und Schriftart der markierten Zeichen ändern.  Mit der <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>\-Eigenschaft können Sie die Farbe der markierten Zeichen ändern.  
  
### So ändern Sie die Darstellung von Zeichen  
  
1.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>\-Eigenschaft eine geeignete Schriftart fest.  
  
     Um Benutzern das Festlegen von Schriftfamilie, Schriftgrad und Schriftschnitt in einer Anwendung zu ermöglichen, wird normalerweise die <xref:System.Windows.Forms.FontDialog>\-Komponente verwendet.  Eine Übersicht finden Sie unter [Übersicht über die FontDialog\-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>\-Eigenschaft eine geeignete Farbe fest.  
  
     Um Benutzern das Festlegen der Farbe in einer Anwendung zu ermöglichen, wird normalerweise die <xref:System.Windows.Forms.ColorDialog>\-Komponente verwendet.  Eine Übersicht finden Sie unter [Übersicht über die ColorDialog\-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Diese Eigenschaften wirken sich nur auf markierten Text aus bzw., wenn kein Text markiert ist, auf den Text, der an der aktuellen Position der Einfügemarke eingegeben wird.  Informationen über das programmgesteuerte Markieren von Text finden Sie unter [TextBoxBase.Select\-Methode](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)