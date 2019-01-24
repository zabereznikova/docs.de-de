---
title: Benutzereingabe in einer Windows Forms-Anwendung
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: a47a35cffb99648737245031a558db884024c011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684079"
---
# <a name="user-input-in-a-windows-forms-application"></a>Benutzereingabe in einer Windows Forms-Anwendung
In Windows Forms wird eine Benutzereingabe an Anwendungen in Form von Windows-Nachrichten gesendet. Eine Reihe von überschreibbaren Methoden verarbeitet diese Nachrichten in der Anwendung, die Form, und steuern. Wenn diese Methoden Maus-und tastaturmeldungen erhalten, auslösen diese Ereignisse, die zum Abrufen von Informationen über die Maus oder Tastatur Eingabe behandelt werden können. In vielen Fällen werden Windows Forms-Anwendungen können alle Benutzereingaben zu verarbeiten, indem Sie einfach die Bearbeitung dieser Ereignisse. In anderen Fällen kann eine Anwendung muss, um eine der Methoden überschreiben, die Verarbeitung von Nachrichten aus, um eine bestimmte Nachricht abzufangen, bevor sie von der Anwendung, Formular oder Steuerelement empfangen wird.  
  
## <a name="mouse-and-keyboard-events"></a>Maus- und Tastaturereignissen  
 Alle Windows Forms-Steuerelemente erben, einen Satz von Ereignissen im Zusammenhang mit der Maus und Tastatur. Z. B. ein Steuerelement behandeln kann die <xref:System.Windows.Forms.Control.KeyPress> Ereignis, um den Zeichencode der einen Schlüssel zu ermitteln, die gedrückt wurde, oder ein Steuerelement kann verarbeiten die <xref:System.Windows.Forms.Control.MouseClick> Ereignis, um zu bestimmen, der Speicherort der Maus klicken Sie auf. Weitere Informationen zu den Ereignissen mit Maus und Tastatur finden Sie unter [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md) und [Mausereignisse in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Methoden, die Benutzer eingehende Nachrichten zu verarbeiten  
 Formulare und Steuerelemente haben Sie Zugriff auf die <xref:System.Windows.Forms.IMessageFilter> -Schnittstelle und eine Reihe von überschreibbare Methoden, die Windows-Nachrichten an verschiedenen Punkten in der Nachrichtenwarteschlange verarbeiten. Diese Methoden alle verfügen über eine <xref:System.Windows.Forms.Message> -Parameter, der kapselt die Details auf niedriger Ebene, der Windows-Meldungen. Sie können zu implementieren oder Überschreiben dieser Methoden, um die Nachricht überprüfen und verarbeiten die Nachricht oder an der nächste Consumer in die Warteschlange übergeben. Die folgende Tabelle enthält die Methoden, die alle Windows-Nachrichten in Windows Forms zu verarbeiten.  
  
|Methode|Hinweise|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Diese Methode fängt die in der Warteschlange (auch bekannt als bereitgestellte) Windows-Nachrichten auf Anwendungsebene ab.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Diese Methode fängt die Windows-Nachrichten auf dem Formular und Steuerelement-Ebene ab, bevor sie verarbeitet wurden.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Diese Methode verarbeitet Windows-Nachrichten auf dem Formular und Steuerelement-Ebene.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Diese Methode führt die standardverarbeitung von Windows-Meldungen auf der Ebene Formular und Steuerelement. Dadurch wird die minimale Funktionalität eines Fensters.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Diese Methode fängt die Nachrichten auf der Ebene Formular und Steuerelement ab, nachdem sie verarbeitet wurden. Die <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> Formatbit muss festgelegt werden, damit diese Methode aufgerufen werden.|  
  
 Tastatur und Maus-Nachrichten werden ebenfalls durch einen zusätzlichen Satz von überschreibbaren Methoden verarbeitet, die den Typen von Nachrichten spezifisch sind. Weitere Informationen finden Sie unter [Funktionsweise von Tastatureingaben](../../../docs/framework/winforms/how-keyboard-input-works.md) und [Maus Funktionsweise in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch
- [Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)
- [Tastatureingaben in einer Windows Forms-Anwendung](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
- [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
