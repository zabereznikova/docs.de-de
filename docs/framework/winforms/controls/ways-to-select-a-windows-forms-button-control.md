---
title: Möglichkeiten zum Auswählen eines Schaltflächen-Steuer Elements
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740003"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Methoden zur Auswahl eines Button-Steuerelements in Windows Forms
Eine Schaltfläche "Windows Forms" kann auf folgende Weise ausgewählt werden:  
  
- Klicken Sie mit der Maus auf die Schaltfläche.  
  
- Rufen Sie das <xref:System.Windows.Forms.Control.Click>-Ereignis der Schaltfläche im Code auf.  
  
- Verschieben Sie den Fokus auf die Schaltfläche, indem Sie die Tab-Taste drücken, und wählen Sie dann die Schaltfläche durch Drücken der Leertaste oder EINGABETASTE aus.  
  
- Drücken Sie die Zugriffstaste (alt + den unterstrichenen Buchstaben) für die Schaltfläche. Weitere Informationen zu Zugriffs Schlüsseln finden Sie unter Gewusst [wie: Erstellen von Zugriffs Schlüsseln für Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)-Steuerelemente.  
  
- Wenn die Schaltfläche die "Accept"-Schaltfläche des Formulars ist, wählt durch Drücken der EINGABETASTE die Schaltfläche aus. Dies gilt auch dann, wenn ein anderes Steuerelement den Fokus besitzt – es sei denn, das andere Steuerelement ist eine andere Schaltfläche, ein mehrzeilige Textfeld oder ein benutzerdefiniertes Steuerelement  
  
- Wenn die Schaltfläche die Schaltfläche "Abbrechen" im Formular ist, wählt die Taste ESC die Schaltfläche aus, auch wenn ein anderes Steuerelement den Fokus besitzt.  
  
- Ruft die <xref:System.Windows.Forms.Button.PerformClick%2A>-Methode auf, um die Schaltfläche Programm gesteuert auszuwählen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Button-Steuerelement](button-control-windows-forms.md)
