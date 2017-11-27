---
title: "Methoden zur Auswahl eines Button-Steuerelements in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08b5359446a80da257f5afec07cc70e3d4aad46b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Methoden zur Auswahl eines Button-Steuerelements in Windows Forms
Eine Windows Forms-Schaltfläche kann auf folgende Weise ausgewählt werden:  
  
-   Verwenden Sie eine Maus, um auf die Schaltfläche klicken.  
  
-   Rufen Sie der Schaltfläche <xref:System.Windows.Forms.Control.Click> Ereignis im Code.  
  
-   Verschieben Sie den Fokus auf die Schaltfläche mit den durch Drücken der TAB-Taste, und wählen Sie dann die Schaltfläche mit den durch Drücken der LEERTASTE oder EINGABETASTE.  
  
-   Drücken Sie die Zugriffstaste (ALT + unterstrichener Buchstabe) für die Schaltfläche aus. Weitere Informationen zu Zugriffstasten finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Wenn die Schaltfläche "" die Schaltfläche "Annehmen" des Formulars ist, durch Drücken der EINGABETASTE auswählt, die Schaltfläche "", auch wenn ein anderes Steuerelement den Fokus besitzt, außer wenn andere Steuerelements ist eine weitere Schaltfläche, ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE aufgefangen.  
  
-   Ist die Schaltfläche "" auf die Schaltfläche "Abbrechen", des Formulars, wählt das Drücken von ESC die Schaltfläche, auch wenn ein anderes Steuerelement den Fokus besitzt.  
  
-   Rufen Sie die <xref:System.Windows.Forms.Button.PerformClick%2A> Methode, um programmgesteuert auf die Schaltfläche klicken.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
