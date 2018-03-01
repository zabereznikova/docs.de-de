---
title: "Übersicht über die ColorDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5df0d7ddd16de5bd8bb052c09731df6583ca4903
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="colordialog-component-overview-windows-forms"></a>Übersicht über die ColorDialog-Komponente (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ColorDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, das den Benutzer um eine Farbe aus einer Palette auszuwählen und Hinzufügen von benutzerdefinierten Farben zu dieser Palette ermöglicht. Es entspricht dem Dialogfeld, das in anderen Windows-basierten Anwendungen zur Farbauswahl angezeigt wird. Verwenden Sie es in Ihrer auf Windows basierenden Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Klicken Sie im Dialogfeld ausgewählte Farbe wird zurückgegeben, der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `false`, die Schaltfläche "Benutzerdefinierte Farben" deaktiviert, sodass der Benutzer auf die vordefinierte Farben in der Palette beschränkt ist. Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht Dithering Farben auswählen. Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
