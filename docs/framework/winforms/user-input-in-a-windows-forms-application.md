---
title: Benutzereingabe in einer Windows Forms-App
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734808"
---
# <a name="user-input-in-a-windows-forms-application"></a>Benutzereingabe in einer Windows Forms-Anwendung
In Windows Forms wird die Benutzereingabe in Form von Windows-Meldungen an Anwendungen gesendet. Eine Reihe von über schreibbaren Methoden verarbeitet diese Nachrichten auf Anwendungs-, Formular-und Steuerelement Ebene. Wenn diese Methoden Maus-und Tastatur Meldungen empfangen, werden Ereignisse ausgegeben, die behandelt werden können, um Informationen über die Maus oder die Tastatureingabe zu erhalten. In vielen Fällen können Windows Forms Anwendungen alle Benutzereingaben verarbeiten, indem Sie diese Ereignisse einfach verarbeiten. In anderen Fällen muss eine Anwendung möglicherweise eine der Methoden überschreiben, die Nachrichten verarbeiten, um eine bestimmte Nachricht abzufangen, bevor Sie von der Anwendung, dem Formular oder dem Steuerelement empfangen wird.  
  
## <a name="mouse-and-keyboard-events"></a>Maus-und Tastatur Ereignisse  
 Alle Windows Forms-Steuerelemente erben eine Reihe von Ereignissen im Zusammenhang mit Maus-und Tastatureingaben. Ein Steuerelement kann z. b. das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis behandeln, um den Zeichencode einer Taste zu bestimmen, die gedrückt wurde, oder ein Steuerelement kann das <xref:System.Windows.Forms.Control.MouseClick> Ereignis verarbeiten, um die Position eines Mausklicks zu bestimmen. Weitere Informationen über die Maus-und Tastatur Ereignisse finden [Sie unter Verwenden von Tastatur Ereignissen](using-keyboard-events.md) und [Mausereignissen in Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Methoden zum Verarbeiten von Benutzereingabe Meldungen  
 Formulare und Steuerelemente haben Zugriff auf die <xref:System.Windows.Forms.IMessageFilter>-Schnittstelle und einen Satz von über schreibbaren Methoden, die Windows-Meldungen an verschiedenen Punkten in der Nachrichten Warteschlange verarbeiten. Diese Methoden verfügen alle über einen <xref:System.Windows.Forms.Message>-Parameter, der die Details von Windows-Meldungen auf niedriger Ebene kapselt. Sie können diese Methoden implementieren oder außer Kraft setzen, um die Nachricht zu untersuchen und anschließend die Nachricht zu verarbeiten oder an den nächsten Consumer in der Nachrichten Warteschlange zu übergeben. In der folgenden Tabelle werden die Methoden dargestellt, die alle Windows-Meldungen in Windows Forms verarbeiten.  
  
|Methode|Notizen|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Diese Methode fängt in die Warteschlange eingereihte Windows-Nachrichten auf Anwendungsebene ab.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Diese Methode fängt Windows-Meldungen auf der Formular-und Steuerelement Ebene ab, bevor Sie verarbeitet wurden.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Diese Methode verarbeitet Windows-Meldungen auf Formular-und Steuerelement Ebene.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Diese Methode führt die Standard Verarbeitung von Windows-Meldungen auf der Formular-und der Steuerelement Ebene aus. Dadurch wird die minimale Funktionalität eines Fensters bereitstellt.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Diese Methode fängt Nachrichten auf der Formular-und Steuerelement Ebene ab, nachdem Sie verarbeitet wurden. Das <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> Stilbit muss festgelegt werden, damit diese Methode aufgerufen wird.|  
  
 Tastatur-und Maus Meldungen werden auch von einem zusätzlichen Satz von über schreibbaren Methoden verarbeitet, die für diese Nachrichten Typen spezifisch sind. Weitere Informationen finden Sie unter [Funktionsweise von Tastatureingaben](how-keyboard-input-works.md) und [Funktionsweise von Maus Eingaben in Windows Forms](how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzereingaben in Windows Forms](user-input-in-windows-forms.md)
- [Tastatureingaben in einer Windows Forms-Anwendung](keyboard-input-in-a-windows-forms-application.md)
- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
