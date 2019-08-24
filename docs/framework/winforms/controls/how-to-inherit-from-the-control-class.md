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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02c40e310778bd476742f62ee8b9d8598b084a53
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015858"
---
# <a name="how-to-inherit-from-the-control-class"></a>Vorgehensweise: Erben von der Control-Klasse

Wenn Sie ein vollständig benutzerdefiniertes Steuerelement erstellen möchten, das in einem Windows Form verwendet werden soll <xref:System.Windows.Forms.Control> , sollten Sie von der-Klasse erben. Obwohl die Vererbung von <xref:System.Windows.Forms.Control> der-Klasse erfordert, dass Sie mehr Planung und Implementierung durchführen, bietet Sie Ihnen auch die größte Palette von Optionen. Wenn Sie von <xref:System.Windows.Forms.Control>erben, erben Sie die grundlegende Funktionalität, mit der Steuerelemente funktionieren. Die Funktionalität, die in <xref:System.Windows.Forms.Control> der-Klasse enthalten ist, verarbeitet Benutzereingaben über Tastatur und Maus, definiert die Begrenzungen und die Größe des Steuer Elements, stellt ein Windows-Handle bereit und bietet Nachrichten Behandlung und Sicherheit. Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion. Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.

## <a name="to-create-a-custom-control"></a>So erstellen Sie ein benutzerdefiniertes Steuerelement

1. Erstellen Sie in Visual Studio eine neue **Windows-Anwendung** oder ein **Windows-Steuerelement Bibliothek** -Projekt.

2. Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.

3. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.

   Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.

4. Drücken Sie **F7** , um den **Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.

5. <xref:System.Windows.Forms.Control.OnPaint%2A> Suchen<xref:System.Windows.Forms.Control.OnPaint%2A> Sie die-Methode, die mit Ausnahme eines Aufrufes der-Methode der-Basisklasse leer ist.

6. Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.

   Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).

7. Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.

8. Speichern und testen Sie das Steuerelement.

## <a name="see-also"></a>Siehe auch

- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
- [Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Von vorhandenen Windows Forms Steuerelementen erben](how-to-inherit-from-existing-windows-forms-controls.md)
- [Vorgehensweise: Steuerelemente für Windows Forms erstellen](how-to-author-controls-for-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
