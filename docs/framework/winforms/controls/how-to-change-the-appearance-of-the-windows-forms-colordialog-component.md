---
title: "Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11edb1019b8fedde368d712ab27dd0954a2de50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms
Sie können die Darstellung von Windows Forms konfigurieren <xref:System.Windows.Forms.ColorDialog> Komponente mit dem eine Reihe von seiner Eigenschaften. Das Dialogfeld enthält zwei Abschnitte – eines, das anzeigt, Grundfarben und eine, die dem Benutzer ermöglicht, benutzerdefinierte Farben definieren.  
  
 Die meisten Eigenschaften einschränken, welche Farben im Dialogfeld die Benutzer auswählen kann. Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `true`, den der Benutzer benutzerdefinierte Farben definieren. Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Eigenschaft `true` verwenden, wenn das Dialogfeld, zum Definieren benutzerdefinierter Farben erweitert wird; andernfalls der Benutzer muss klicken Sie auf eine Schaltfläche "Benutzerdefinierte Farben definieren". Wenn die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> -Eigenschaftensatz auf `true`, das Dialogfeld zeigt alle verfügbare Farben in der Menge der Grundfarben. Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht Dithering Farben auswählen; nur Volltonfarben stehen zur Auswahl.  
  
 Wenn die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> -Eigenschaftensatz auf `true`, eine Schaltfläche "Hilfe" im Dialogfeld angezeigt wird. Wenn der Benutzer die Schaltfläche "Hilfe" klickt der <xref:System.Windows.Forms.ColorDialog> Komponente <xref:System.Windows.Forms.CommonDialog.HelpRequest> Ereignis wird ausgelöst.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>So konfigurieren Sie die Darstellung im Dialogfeld "Farbe"  
  
1.  Legen Sie die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> Eigenschaften auf die gewünschten Werte.  
  
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
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Übersicht über die ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
