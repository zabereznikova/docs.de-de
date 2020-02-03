---
title: Mausaufzeichnung
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741022"
---
# <a name="mouse-capture-in-windows-forms"></a>Mauserfassung in Windows Forms
Die *Maus Aufzeichnung* verweist auf, wenn ein Steuerelement den Befehl für alle Maus Eingaben annimmt. Wenn ein Steuerelement die Maus erfasst hat, empfängt es Maus Eingaben, unabhängig davon, ob sich der Zeiger innerhalb seines Rahmens befindet.  
  
## <a name="setting-mouse-capture"></a>Festlegen der Maus Aufzeichnung  
 In Windows Forms die Maus vom Steuerelement aufgezeichnet, wenn der Benutzer eine Maustaste auf ein Steuerelement drückt, und die Maus wird vom-Steuerelement losgelassen, wenn der Benutzer die Maustaste loslässt.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A>-Eigenschaft der <xref:System.Windows.Forms.Control>-Klasse gibt an, ob ein Steuerelement die Maus erfasst hat. Behandeln Sie das <xref:System.Windows.Forms.Control.MouseCaptureChanged>-Ereignis, um zu bestimmen, wann ein Steuerelement die Maus Aufzeichnung verliert.  
  
 Nur im Vordergrund Fenster kann die Maus erfasst werden. Wenn ein Hintergrund Fenster versucht, die Maus zu erfassen, empfängt das Fenster nur Meldungen für Mausereignisse, die auftreten, wenn sich der Mauszeiger innerhalb des sichtbaren Teils des Fensters befindet. Auch wenn das Vordergrund Fenster die Maus erfasst hat, kann der Benutzer weiterhin auf ein anderes Fenster klicken, um ihn in den Vordergrund zu bringen. Wenn die Maus aufgezeichnet wird, funktionieren Tastenkombinationen nicht.  
  
## <a name="see-also"></a>Weitere Informationen

- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
