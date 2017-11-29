---
title: Benutzereingabe in einer Windows Forms-Anwendung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb6f832b77404b57ab22e4ac472e7707f0e10dd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="user-input-in-a-windows-forms-application"></a>Benutzereingabe in einer Windows Forms-Anwendung
In Windows Forms wird eine Benutzereingabe an Anwendungen in Form von Windows-Nachrichten gesendet. Eine Reihe von überschreibbaren Methoden verarbeiten diese Nachrichten an die Anwendung, Form, und Steuern der Ebene. Wenn diese Methoden mit Maus und Tastatur Nachrichten empfangen, lösen sie Ereignisse, die zum Abrufen von Informationen über die Maus oder Tastatur Eingabe behandelt werden können. In vielen Fällen werden Windows Forms-Anwendungen alle Benutzereingaben zu verarbeiten, einfach, indem Sie diese Ereignisse behandeln können. In anderen Fällen muss eine Anwendung möglicherweise eine der Methoden überschreiben, das Verarbeiten von Nachrichten, um eine bestimmte Nachricht abfangen zu können, bevor es von der Anwendung, Formular oder Steuerelement empfangen wird.  
  
## <a name="mouse-and-keyboard-events"></a>Maus- und Tastaturereignissen  
 Alle Windows Forms-Steuerelemente erben, einen Satz von Ereignissen im Zusammenhang mit Maus- und Tastatureingaben. Angenommen, ein Steuerelement behandeln kann die <xref:System.Windows.Forms.Control.KeyPress> Ereignis, um den Zeichencode eines Schlüssels zu bestimmen, die gedrückt wurde oder ein Steuerelement behandeln kann die <xref:System.Windows.Forms.Control.MouseClick> Ereignis, um zu bestimmen, die Position eines Mausklicks klicken Sie auf. Weitere Informationen zu den Ereignissen mit Maus und Tastatur finden Sie unter [mithilfe von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md) und [Mausereignisse in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Methoden, mit denen Benutzer eingehende Nachrichten zu verarbeiten.  
 Formulare und Steuerelemente haben Sie Zugriff auf die <xref:System.Windows.Forms.IMessageFilter> Schnittstelle und einen Satz von überschreibbaren Methoden, die Windows-Meldungen an unterschiedlichen Positionen in der Nachrichtenwarteschlange verarbeiten. Diese Methoden alle verfügen über eine <xref:System.Windows.Forms.Message> -Parameter, der die Details auf niedriger Ebene des Windows-Meldungen kapselt. Sie können implementieren oder überschreiben Sie diese Methoden überprüfen Sie die Meldung an und klicken Sie dann entweder die Nachricht verarbeiten oder an den nächsten Consumer in der Meldungswarteschlange übergeben. Die folgende Tabelle enthält die Methoden, die alle Windows-Meldungen in Windows Forms zu verarbeiten.  
  
|Methode|Hinweise|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Diese Methode fängt Nachrichten in der Warteschlange (auch bekannt als gebuchten) Windows auf Anwendungsebene ab.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Diese Methode fängt die Ebene der Formular- und Windows-Meldungen ab, bevor diese verarbeitet wurden.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Diese Methode verarbeitet Windows-Meldungen auf dem Formular und jedes Steuerelement-Ebene.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Diese Methode führt die standardverarbeitung von Windows-Nachrichten auf der Ebene Formular und jedes Steuerelement. Dies bietet die grundlegenden Funktionen eines Fensters.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Diese Methode fängt Nachrichten auf der Ebene Formular und jedes Steuerelement ab, nachdem sie verarbeitet wurden. Die <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> Formatbit muss festgelegt werden, damit diese Methode aufgerufen werden.|  
  
 Tastatur und Maus Nachrichten werden ebenfalls durch einen zusätzlichen Satz von überschreibbaren Methoden verarbeitet, die speziell für diese Typen von Nachrichten sind. Weitere Informationen finden Sie unter [Funktionsweise von Tastatureingaben](../../../docs/framework/winforms/how-keyboard-input-works.md) und [Maus Funktionsweise in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [Tastatureingaben in einer Windows Forms-Anwendung](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
