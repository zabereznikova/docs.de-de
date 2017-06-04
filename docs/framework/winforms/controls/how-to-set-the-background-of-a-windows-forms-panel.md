---
title: "Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs | Microsoft Docs"
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
  - "Hintergrundfarben, Panel-Steuerelemente in Windows Forms"
  - "Hintergrundbilder, Panel-Steuerelemente in Windows Forms"
  - "Farben, Panel-Steuerelemente in Windows Forms"
  - "Panel-Steuerelement [Windows Forms], Hintergrund"
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs
Mithilfe eines <xref:System.Windows.Forms.Panel>\-Steuerelements kann in Windows Forms sowohl eine Hintergrundfarbe als auch ein Hintergrundbild angezeigt werden.  Über die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft wird die Hintergrundfarbe der enthaltenen Steuerelemente, wie Bezeichnungsfelder und Optionsfelder, festgelegt.  Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft nicht festgelegt wird, füllt die <xref:System.Windows.Forms.Control.BackColor%2A>\-Auswahl den gesamten Auswahlbereich aus.  Ist die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft jedoch festgelegt, wird das Bild hinter den enthaltenen Steuerelementen angezeigt.  
  
### So legen Sie den Hintergrund programmgesteuert fest  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft des Bereichs einen Wert vom Typ <xref:System.Drawing.Color?displayProperty=fullName> fest.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft des Bereichs mit der <xref:System.Drawing.Image.FromFile%2A>\-Methode der <xref:System.Drawing.Image?displayProperty=fullName>\-Klasse fest.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)