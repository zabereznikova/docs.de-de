---
title: Drag & amp; Drop-Funktionalität
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
ms.openlocfilehash: 603dc158719c0b11def4386eb24a33f235cf3a42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732759"
---
# <a name="drag-and-drop-functionality-in-windows-forms"></a>Drag &amp; Drop-Funktionen in Windows Forms
Windows Forms umfasst eine Reihe von Methoden, Ereignissen und Klassen, die das Drag &amp; Drop-Verhalten implementieren. Dieses Thema enthält eine Übersicht über die Drag &amp; Drop-Unterstützung in Windows Forms.  Siehe auch [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](./advanced/drag-and-drop-operations-and-clipboard-support.md).  
  
## <a name="performing-drag-and-drop-operations"></a>Ausführen von Drag &amp; Drop-Vorgängen  
 Um einen Drag &amp; Drop-Vorgang auszuführen, verwenden Sie die <xref:System.Windows.Forms.Control.DoDragDrop%2A>-Methode der <xref:System.Windows.Forms.Control>-Klasse. Weitere Informationen, wie ein Drag &amp; Drop-Vorgang ausgeführt wird, finden Sie unter <xref:System.Windows.Forms.Control.DoDragDrop%2A>. Um das Rechteck abzurufen, über das der Mauszeiger gezogen werden muss, bevor ein Drag &amp; Drop-Vorgang beginnt, verwenden Sie die <xref:System.Windows.Forms.SystemInformation.DragSize%2A>-Eigenschaft der <xref:System.Windows.Forms.SystemInformation>-Klasse.  
  
## <a name="events-related-to-drag-and-drop-operations"></a>Ereignisse im Zusammenhang mit Drag &amp; Drop-Vorgängen  
 Es gibt zwei Kategorien von Ereignissen in einem Drag & Drop-Vorgang: Ereignisse, die im aktuellen Ziel des Drag &amp; Drop-Vorgangs auftreten, und Ereignisse, die in der Quelle des Drag &amp; Drop-Vorgangs auftreten.  
  
### <a name="events-on-the-current-target"></a>Ereignisse im aktuellen Ziel  
 Die folgende Tabelle zeigt die Ereignisse, die im aktuellen Ziel eines Drag &amp; Drop--Vorgangs auftreten.  
  
|Mausereignis|BESCHREIBUNG|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|Dieses Ereignis tritt auf, wenn ein Objekt in die Begrenzungen des Steuerelements gezogen wird. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragOver>|Dieses Ereignis tritt auf, wenn ein Objekt gezogen wird, während sich der Mauszeiger innerhalb der Grenzen des Steuerelements befindet. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragDrop>|Dieses Ereignis tritt auf, wenn ein Drag &amp; Drop-Vorgang abgeschlossen wurde. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragLeave>|Dieses Ereignis tritt auf, wenn ein Objekt über die Grenzen des Steuerelements nach außen gezogen wird. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
  
 Die <xref:System.Windows.Forms.DragEventArgs>-Klasse stellt die Position des Mauszeigers, den aktuellen Zustand der Maustasten und der Zusatztasten der Tastatur, die gezogenen Daten und die <xref:System.Windows.Forms.DragDropEffects>-Werte bereit, die die Vorgänge, die für die Quelle des Ziehereignisses zulässig sind, sowie den Zielablegeeffekt für den Vorgang angeben.  
  
### <a name="events-on-the-source"></a>Ereignisse in der Quelle  
 Die folgende Tabelle zeigt die Ereignisse, die in der Quelle eines Drag &amp; Drop-Vorgangs auftreten.  
  
|Mausereignis|BESCHREIBUNG|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|Dieses Ereignis tritt während eines Ziehvorgangs auf. Es bietet die Möglichkeit, dem Benutzer einen visuellen Hinweis zu geben, dass der Drag &amp; Drop-Vorgang auftritt, z. B. Ändern des Mauszeigers. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.GiveFeedbackEventArgs>.|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|Dieses Ereignis wird während eines Drag & Drop-Vorgangs ausgelöst. Dadurch kann die Quelle des Ziehvorgangs bestimmen, ob der Drag &amp;amp; Drop-Vorgang abgebrochen werden soll. Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.QueryContinueDragEventArgs>.|  
  
 Die <xref:System.Windows.Forms.QueryContinueDragEventArgs>-Klasse stellt Folgendes bereit: den aktuellen Zustand der Maus und der Zusatztasten der Tastatur, einen Wert, der angibt, ob die ESC-Taste gedrückt wurde, und einen <xref:System.Windows.Forms.DragAction>-Wert, der festgelegt werden kann, um anzugeben, ob der Drag &amp; Drop-Vorgang fortgesetzt werden soll.  
  
## <a name="see-also"></a>Weitere Informationen

- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
