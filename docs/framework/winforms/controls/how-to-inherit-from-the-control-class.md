---
title: "Gewusst wie: Erben von der Control-Klasse | Microsoft Docs"
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
  - "Control-Klasse, Erben von"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Erstellen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Vererbung"
  - "Vererbung, Benutzerdefinierte Windows Forms-Steuerelemente"
  - "OnPaint-Methode [Windows Forms]"
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erben von der Control-Klasse
Wenn ein vollständig benutzerdefiniertes Steuerelement erstellt werden soll, um in Windows Forms verwendet zu werden, sollten Sie von der <xref:System.Windows.Forms.Control>\-Klasse erben.  Das Erben von der <xref:System.Windows.Forms.Control>\-Klasse setzt zwar eine umfangreichere Planung und Implementierung voraus, bietet Ihnen aber auch die größtmögliche Auswahl an Optionen.  Mit dem Erben von <xref:System.Windows.Forms.Control> wird die reine Basisfunktionalität geerbt, die für das Funktionieren des Steuerelements erforderlich ist.  Mit der Funktionalität, die der <xref:System.Windows.Forms.Control>\-Klasse inhärent ist, werden Benutzereingaben über Tastatur und Maus behandelt, Rahmen und Größe der Steuerelemente definiert und ein Fensterhandle sowie Meldungsbehandlung und Sicherheit geboten.  Zeichnen, also in diesem Fall das tatsächliche Rendering der grafischen Oberfläche des Steuerelements, ist ebenso wenig eingebunden wie besondere Funktionalität bezüglich der Benutzerinteraktion.  Diese Aspekte müssen Sie über benutzerdefinierten Code bereitstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein benutzerdefiniertes Steuerelement  
  
1.  Erstellen Sie ein neues **Windows\-Anwendung**\-Projekt oder **Windows\-Steuerelementbibliothek**\-Projekt.  
  
2.  Klicken Sie im Menü **Projekt** auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.  
  
     Ein neues benutzerdefiniertes Steuerelement wird dem Projekt hinzugefügt.  
  
4.  Drücken Sie F7, um den **Code\-Editor** für das benutzerdefinierte Steuerelement zu öffnen.  
  
5.  Suchen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, die bis auf einen Aufruf der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse leer sein wird.  
  
6.  Bearbeiten Sie den Code, um das für das Steuerelement gewünschte benutzerdefinierte Zeichnen einzubinden.  
  
     Informationen über das Schreiben von Code zum Rendering von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
7.  Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden.  
  
8.  Speichern und testen Sie das Steuerelement.  
  
## Siehe auch  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Gewusst wie: Erben von der UserControl\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Gewusst wie: Erben von vorhandenen Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)