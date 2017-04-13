---
title: "Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers | Microsoft Docs"
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
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers
Mithilfe eines <xref:System.Windows.Forms.Panel>\-Steuerelements kann in Windows Forms sowohl eine Hintergrundfarbe als auch ein Hintergrundbild angezeigt werden.  Über die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft wird die Hintergrundfarbe der im Bereich enthaltenen Steuerelemente, z. B. Bezeichnungsfelder und Optionsfelder, festgelegt.  Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft nicht festgelegt wird, füllt die <xref:System.Windows.Forms.Control.BackColor%2A>\-Auswahl den gesamten Auswahlbereich aus.  Ist die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft jedoch festgelegt, wird das Bild hinter den im Bereich enthaltenen Steuerelementen angezeigt.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.Panel>\-Steuerelement enthält.  Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie den Hintergrund im Windows Forms\-Designer fest  
  
1.  Wählen Sie das <xref:System.Windows.Forms.Panel>\-Steuerelement aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Pfeilschaltfläche neben der <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft, um ein Fenster mit drei Registerkarten anzuzeigen.  
  
3.  Wählen Sie die Registerkarte **Benutzerdefiniert** aus, um eine Farbpalette anzuzeigen.  
  
4.  Wählen Sie die Registerkarte **Web** oder **System** aus, um eine Liste mit vordefinierten Farbbezeichnungen anzuzeigen, und wählen Sie dann eine Farbe aus.  
  
5.  Klicken Sie im **Eigenschaftenfenster** auf die Pfeilschaltfläche neben der <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft.  
  
6.  Wählen Sie im Dialogfeld **Öffnen** die Datei aus, die Sie anzeigen möchten.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms\-Bereichssteuerelement im Designer](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)