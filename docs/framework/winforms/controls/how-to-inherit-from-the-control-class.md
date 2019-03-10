---
title: 'Vorgehensweise: Erben von der Control-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: cf1b3c7d7d530710c4c7e0fbd137667c3598500a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702970"
---
# <a name="how-to-inherit-from-the-control-class"></a>Vorgehensweise: Erben von der Control-Klasse
Wenn Sie ein vollständig benutzerdefiniertes Steuerelement für die Verwendung in einem Windows Form erstellen möchten, sollten Sie erben von der <xref:System.Windows.Forms.Control> Klasse. Beim Erben von der <xref:System.Windows.Forms.Control> Klasse erfordert mehr Planung und Implementierung durchführen, es bietet Ihnen auch die größtmögliche Auswahl an Optionen. Beim Erben von <xref:System.Windows.Forms.Control>, erben die grundlegende Funktionalität, die Steuerelemente notwendig ist. Die Funktionalität der <xref:System.Windows.Forms.Control> Klasse behandelt Benutzereingaben durch Tastatur und Maus, definiert die Grenzen und die Größe des Steuerelements, stellt ein Windows-Handle bereit und bietet Meldungsbehandlung und Sicherheit. Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion. Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-custom-control"></a>So erstellen Sie ein benutzerdefiniertes Steuerelement  
  
1.  Erstellen Sie ein neues **Windows-Anwendung** oder **Windows-Steuerelementbibliothek**-Projekt.  
  
2.  Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.  
  
3.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.  
  
     Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.  
  
4.  Drücken Sie F7, um den**Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.  
  
5.  Suchen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, die leer ist, mit Ausnahme von einem Aufruf der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse.  
  
6.  Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.  
  
     Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).  
  
7.  Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.  
  
8.  Speichern und testen Sie das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
- [Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](how-to-inherit-from-existing-windows-forms-controls.md)
- [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
