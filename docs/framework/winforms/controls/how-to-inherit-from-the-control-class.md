---
title: 'Gewusst wie: Erben von der Control-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458382"
---
# <a name="how-to-inherit-from-the-control-class"></a>Gewusst wie: Erben von der Control-Klasse

Wenn Sie ein vollständig benutzerdefiniertes Steuerelement erstellen möchten, das in einem Windows Form verwendet werden soll, sollten Sie von der <xref:System.Windows.Forms.Control>-Klasse erben. Obwohl die Vererbung von der <xref:System.Windows.Forms.Control>-Klasse erfordert, dass Sie mehr Planung und Implementierung durchführen, bietet Sie Ihnen auch die größte Auswahl von Optionen. Wenn Sie von <xref:System.Windows.Forms.Control>erben, erben Sie die grundlegende Funktionalität, die die Steuerung der Steuerelemente ermöglicht. Die Funktionalität, die in der <xref:System.Windows.Forms.Control>-Klasse enthalten ist, verarbeitet Benutzereingaben über Tastatur und Maus, definiert die Begrenzungen und die Größe des Steuer Elements, stellt ein Windows-Handle bereit und bietet Nachrichten Behandlung und-Sicherheit. Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion. Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.

## <a name="to-create-a-custom-control"></a>So erstellen Sie ein benutzerdefiniertes Steuerelement

1. Erstellen Sie in Visual Studio eine neue **Windows-Anwendung** oder ein **Windows-Steuerelement Bibliothek** -Projekt.

2. Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.

3. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.

   Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.

4. Drücken Sie **F7** , um den **Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.

5. Suchen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode, die mit Ausnahme eines Aufrufes der <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode der Basisklasse leer ist.

6. Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.

   Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).

7. Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.

8. Speichern und testen Sie das Steuerelement.

## <a name="see-also"></a>Siehe auch

- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)
- [Gewusst wie: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](how-to-inherit-from-existing-windows-forms-controls.md)
- [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
