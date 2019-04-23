---
title: 'Vorgehensweise: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: d2bb9e06d9d84a9b61c67510e9c012066f69d55e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329231"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Vorgehensweise: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms
Sie können konfigurieren, das Erscheinungsbild der Windows-Formulare <xref:System.Windows.Forms.ColorDialog> Komponente mit dem eine Reihe von dessen Eigenschaften. Das Dialogfeld verfügt über zwei Abschnitte: einen, der anzeigt, Grundfarben und eine, die dem Benutzer ermöglicht, benutzerdefinierte Farben definieren.  
  
 Die meisten Eigenschaften einschränken, welche Farben im Dialogfeld der Benutzer auswählen kann. Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `true`, können Benutzer benutzerdefinierte Farben definieren. Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Eigenschaft `true` Wenn das Dialogfeld wird erweitert, damit benutzerdefinierte Farben definiert werden andernfalls der Benutzer muss klicken Sie auf eine Schaltfläche "Benutzerdefinierte Farben". Wenn die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> -Eigenschaftensatz auf `true`, im Dialogfeld werden alle verfügbare Farben angezeigt, in der Menge der Grundfarben. Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht mit Dithering Farben auswählen, stehen nur Volltonfarben auswählen.  
  
 Wenn die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> -Eigenschaftensatz auf `true`, eine Schaltfläche "Hilfe", die im Dialogfeld wird angezeigt. Wenn der Benutzer die Schaltfläche "Hilfe" klickt der <xref:System.Windows.Forms.ColorDialog> Komponente <xref:System.Windows.Forms.CommonDialog.HelpRequest> Ereignis wird ausgelöst.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>So konfigurieren Sie die Darstellung im Dialogfeld "Farbe"  
  
1. Legen Sie die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> Eigenschaften auf die gewünschten Werte.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog-Komponente](colordialog-component-windows-forms.md)
- [Übersicht über die ColorDialog-Komponente](colordialog-component-overview-windows-forms.md)
