---
title: 'Gewusst wie: Erben von der Control-Klasse'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b9c56d2d9df80745cec2b811c39f5e438d07c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-the-control-class"></a>Gewusst wie: Erben von der Control-Klasse
Wenn Sie ein vollständig benutzerdefiniertes Steuerelement für die Verwendung in einem Windows Form erstellen möchten, sollten Sie erben von der <xref:System.Windows.Forms.Control> Klasse. Beim Erben von der <xref:System.Windows.Forms.Control> Klasse erfordert, dass Sie ausführen, Planung und Implementierung bereit, sondern auch Sie mit der größten Palette von Optionen. Beim Erben von <xref:System.Windows.Forms.Control>, Sie erben die Basisfunktionalität, die Steuerelemente, die verwendet wird. Die Funktionalität, die eine inhärente Eigenschaft der <xref:System.Windows.Forms.Control> Klasse behandelt Benutzereingaben über die Tastatur und Maus, definiert die Grenzen und die Größe des Steuerelements stellt ein Windows-Handle und Meldungsbehandlung und Sicherheit. Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion. Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-custom-control"></a>So erstellen Sie ein benutzerdefiniertes Steuerelement  
  
1.  Erstellen Sie ein neues **Windows-Anwendung** oder **Windows-Steuerelementbibliothek**-Projekt.  
  
2.  Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.  
  
3.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.  
  
     Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.  
  
4.  Drücken Sie F7, um den**Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.  
  
5.  Suchen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, die mit Ausnahme von einem Aufruf von leer sein wird die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse.  
  
6.  Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.  
  
     Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
7.  Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.  
  
8.  Speichern und testen Sie das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Vorgehensweise: Erben von der UserControl-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
