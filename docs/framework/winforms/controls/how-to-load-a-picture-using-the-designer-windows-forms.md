---
title: "Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms) | Microsoft Docs"
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
  - "Formulare, Anzeigen von Bildern"
  - "Bilder [Windows Forms], Anzeigen in Windows Forms"
  - "Bildformate"
  - "PictureBox-Steuerelement [Windows Forms], Hinzufügen von Bildern"
  - "Bilder, Anzeigen"
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)
Mithilfe des <xref:System.Windows.Forms.PictureBox>\-Steuerelements für Windows Forms kann ein Bild zur Entwurfszeit in ein Formular geladen und darin angezeigt werden. Zu diesem Zweck muss für die <xref:System.Windows.Forms.PictureBox.Image%2A>\-Eigenschaft ein gültiges Bild angegeben werden.  In der folgenden Tabelle werden die gültigen Dateitypen angezeigt.  
  
|Typ|Dateinamenerweiterung|  
|---------|---------------------------|  
|Bitmap|.bmp|  
|Symbol|.ico|  
|GIF|GIF|  
|Metadatei|WMF|  
|JPEG|JPG|  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So lassen Sie ein Bild zur Entwurfszeit anzeigen  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.PictureBox>\-Steuerelement auf ein Formular.  
  
2.  Markieren Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.PictureBox.Image%2A>\-Eigenschaft, und klicken Sie dann auf die Schaltfläche mit den Auslassungszeichen, um das Dialogfeld **Öffnen** anzuzeigen.  
  
3.  Falls Sie einen bestimmten Dateityp suchen \(z. B. GIF\-Dateien\), wählen Sie diesen im Feld **Dateityp** aus.  
  
4.  Wählen Sie die anzuzeigende Datei aus.  
  
### So entfernen Sie ein Bild zur Entwurfszeit  
  
1.  Wählen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.PictureBox.Image%2A>\-Eigenschaft aus, und klicken Sie mit der rechten Maustaste auf die kleine Miniaturansicht, die links neben dem Namen des Bildobjekts angezeigt wird.  Klicken Sie auf **Zurücksetzen**.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PictureBox>   
 [Übersicht über das PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [Gewusst wie: Festlegen von Bildern zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)