---
title: Methoden zur Auswahl eines Button-Steuerelements in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 908751401d812be0403af5517d9bbf2ad7344f35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573802"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Methoden zur Auswahl eines Button-Steuerelements in Windows Forms
Eine Windows Forms-Schaltfläche kann auf folgende Weise ausgewählt werden:  
  
-   Verwenden Sie eine Maus, um auf die Schaltfläche klicken.  
  
-   Rufen Sie der Schaltfläche " <xref:System.Windows.Forms.Control.Click> Ereignis im Code.  
  
-   Den Fokus auf die Schaltfläche mit den durch Drücken der TAB-Taste, und wählen Sie dann die Schaltfläche mit den durch Drücken der LEERTASTE oder EINGABETASTE.  
  
-   Drücken Sie die Zugriffsschlüssel (ALT + unterstrichener Buchstabe) für die Schaltfläche aus. Weitere Informationen zu Zugriffsschlüsseln finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows-Steuerelemente Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Wenn die Schaltfläche des Formulars die Schaltfläche "accept" ist, Drücken der EINGABETASTE auswählt, die Schaltfläche, auch wenn ein anderes Steuerelement den Fokus besitzt, außer wenn das andere Steuerelement ist eine weitere Schaltfläche, ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das fängt die EINGABETASTE.  
  
-   Ist die Schaltfläche mit der auf die Schaltfläche "Abbrechen" des Formulars, wählt das Drücken der ESC-Taste die Schaltfläche, selbst wenn ein anderes Steuerelement den Fokus besitzt.  
  
-   Rufen Sie die <xref:System.Windows.Forms.Button.PerformClick%2A> Methode, um programmgesteuert auf die Schaltfläche klicken.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
