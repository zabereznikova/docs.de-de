---
title: Übersicht über die ColorDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 284d42218fb4fbce873325b1e45c883d51eefab8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956337"
---
# <a name="colordialog-component-overview-windows-forms"></a>Übersicht über die ColorDialog-Komponente (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.ColorDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, das dem Benutzer eine Farbe aus einer Palette auswählen und Hinzufügen von benutzerdefinierten Farben zu dieser Palette ermöglicht. Es entspricht dem Dialogfeld, das in anderen Windows-basierten Anwendungen zur Farbauswahl angezeigt wird. Verwenden Sie es in Ihrer auf Windows basierenden Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Im Dialogfeld ausgewählte Farbe wird zurückgegeben, der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `false`, die Schaltfläche "Benutzerdefinierte Farben" ist deaktiviert, und der Benutzer ist der vordefinierten Farben in der Palette. Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht mit Dithering Farben auswählen. Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog-Komponente](colordialog-component-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](dialog-box-controls-and-components-windows-forms.md)
- [Vorgehensweise: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
