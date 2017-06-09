---
title: "Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Bildes | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Bilder"
  - "Steuerelemente [Windows Forms], Bilder"
  - "Beispiele [Windows Forms], Steuerelemente"
  - "Bilder [Windows Forms], Windows Forms-Steuerelemente"
  - "Windows Forms-Steuerelemente, Bilder"
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Bildes
Einige Windows Forms\-Steuerelemente können Bilder anzeigen.  Diese Bilder können Symbole sein, die den Zweck eines Steuerelements verdeutlichen, z. B. ein Diskettensymbol auf einer Schaltfläche für den Befehl **Speichern**.  Alternativ können die Symbole Hintergrundbilder sein, um dem Steuerelement das gewünschte Aussehen und Verhalten zuzuweisen.  
  
### So legen Sie das von einem Steuerelement angezeigte Bild fest  
  
1.  Legen Sie die `Image`\-Eigenschaft oder die `BackgroundImage`\-Eigenschaft des Steuerelements auf ein Objekt des Typs <xref:System.Drawing.Image> fest.  Im Allgemeinen laden Sie das Bild mithilfe der <xref:System.Drawing.Image.FromFile%2A>\-Methode aus einer Datei.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Bild der Ordner **Eigene Bilder** festgelegt.  Dieses Verzeichnis ist auf den meisten Computer verfügbar, auf denen das Windows\-Betriebssystem ausgeführt wird.  Dieser Speicherort ermöglicht auch Benutzern mit minimalen Systemzugriffsebenen, die Anwendung sicher auszuführen.  Im folgenden Codebeispiel wird vorausgesetzt, dass Sie bereits über ein Formular verfügen, dem das <xref:System.Windows.Forms.PictureBox>\-Steuerelement hinzugefügt wurde.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## Siehe auch  
 <xref:System.Drawing.Image.FromFile%2A>   
 <xref:System.Drawing.Image>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>