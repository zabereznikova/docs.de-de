---
title: Mauserfassung in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690327"
---
# <a name="mouse-capture-in-windows-forms"></a>Mauserfassung in Windows Forms
*Erfassen von Mausereignissen* bezieht sich auf, wenn ein Befehl, der alle Mauseingabe hat. Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.  
  
## <a name="setting-mouse-capture"></a>Die Erfassung von Mauseingaben festlegen  
 In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste auf einem Steuerelement drückt, und die Maus vom Steuerelement freigegeben wird, wenn der Benutzer die Maustaste loslässt.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse gibt an, ob ein Steuerelement die Maus erfasst hat. Um zu bestimmen, wenn ein Steuerelement die Mausauswahl verliert, behandelt der <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.  
  
 Nur das Vordergrundfenster kann die Maus erfassen. Wenn einem Hintergrundfenster versucht, die die Maus erfassen, empfängt das Fenster Nachrichten nur von den Mausereignissen, die auftreten, wenn der Mauszeiger in den sichtbaren Teil des Fensters befindet. Darüber hinaus auch, wenn das Vordergrundfenster die Maus erfasst hat, kann der Benutzer noch einem anderen Fenster klicken es in den Vordergrund zu bringen. Wenn die Maus erfasst wird, funktionieren Tastenkombinationen nicht.  
  
## <a name="see-also"></a>Siehe auch
- [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
