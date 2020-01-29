---
title: Übersicht über die ColorDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736964"
---
# <a name="colordialog-component-overview-windows-forms"></a>Übersicht über die ColorDialog-Komponente (Windows Forms)
Bei der Windows Forms <xref:System.Windows.Forms.ColorDialog> Komponente handelt es sich um ein vorkonfiguriertes Dialogfeld, mit dem der Benutzer eine Farbe aus einer Palette auswählen und dieser Palette benutzerdefinierte Farben hinzufügen kann. Es entspricht dem Dialogfeld, das in anderen Windows-basierten Anwendungen zur Farbauswahl angezeigt wird. Verwenden Sie es in Ihrer auf Windows basierenden Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Die im Dialogfeld ausgewählte Farbe wird in der <xref:System.Windows.Forms.ColorDialog.Color%2A>-Eigenschaft zurückgegeben. Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>-Eigenschaft auf `false`festgelegt ist, wird die Schaltfläche "benutzerdefinierte Farben definieren" deaktiviert, und der Benutzer ist auf die vordefinierten Farben in der Palette beschränkt. Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>-Eigenschaft auf `true`festgelegt ist, kann der Benutzer keine Dithering-Farben auswählen. Um das Dialogfeld anzuzeigen, müssen Sie dessen <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode aufrufen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog-Komponente](colordialog-component-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](dialog-box-controls-and-components-windows-forms.md)
- [Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
