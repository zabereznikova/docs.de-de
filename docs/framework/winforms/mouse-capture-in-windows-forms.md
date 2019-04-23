---
title: Mauserfassung in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 30432c6978f60cc9ad47d5df5dafc7aa45229f3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151644"
---
# <a name="mouse-capture-in-windows-forms"></a>Mauserfassung in Windows Forms
*Erfassen von Mausereignissen* bezieht sich auf, wenn ein Befehl, der alle Mauseingabe hat. Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.  
  
## <a name="setting-mouse-capture"></a>Die Erfassung von Mauseingaben festlegen  
 In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste auf einem Steuerelement drückt, und die Maus vom Steuerelement freigegeben wird, wenn der Benutzer die Maustaste loslässt.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse gibt an, ob ein Steuerelement die Maus erfasst hat. Um zu bestimmen, wenn ein Steuerelement die Mausauswahl verliert, behandelt der <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.  
  
 Nur das Vordergrundfenster kann die Maus erfassen. Wenn einem Hintergrundfenster versucht, die die Maus erfassen, empfängt das Fenster Nachrichten nur von den Mausereignissen, die auftreten, wenn der Mauszeiger in den sichtbaren Teil des Fensters befindet. Darüber hinaus auch, wenn das Vordergrundfenster die Maus erfasst hat, kann der Benutzer noch einem anderen Fenster klicken es in den Vordergrund zu bringen. Wenn die Maus erfasst wird, funktionieren Tastenkombinationen nicht.  
  
## <a name="see-also"></a>Siehe auch

- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
