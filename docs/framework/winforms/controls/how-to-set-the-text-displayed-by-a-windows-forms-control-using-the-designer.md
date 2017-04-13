---
title: "Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Textes mithilfe des Designers | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Festlegen der Beschriftung"
  - "Windows Forms, Festlegen des angezeigten Texts"
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Festlegen des durch ein Windows&#160;Forms-Steuerelement angezeigten Textes mithilfe des Designers
Windows Forms\-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt.  Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>\-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist.  Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft festlegen oder zurückgeben.  Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft verwenden.  
  
### So legen Sie den Text und die Schriftart mithilfe des Designers fest  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des Steuerelements im Eigenschaftenfenster auf eine geeignete Zeichenfolge fest.  
  
     Wenn Sie eine unterstrichene Zugriffstaste erstellen möchten, setzen Sie ein kaufmännisches Und\-Zeichen \(&\) vor den Buchstaben der Zugriffstaste.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit dem Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft befindet.  
  
     Wählen Sie im Standarddialogfeld für Schriftarten Schriftart, Schriftschnitt, Schriftgröße, Effekte \(z. B. Durchgestrichen oder Unterstrichen\) sowie das gewünschte Skript aus.  
  
## Siehe auch  
 [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)