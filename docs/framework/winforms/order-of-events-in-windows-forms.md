---
title: Ereignisreihenfolge in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: 10a6451827a16605ba738cf74b7f684b69adb5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="order-of-events-in-windows-forms"></a>Ereignisreihenfolge in Windows Forms
Die Reihenfolge, in der Ereignisse in Windows Forms-Anwendungen ausgelöst werden, ist für Entwickler von besonderem Interesse, die sich mit der sukzessiven Verarbeitung jedes dieser Ereignisse befassen müssen. Wenn eine Situation die sorgfältige Verarbeitung von Ereignissen erfordert, z. B. beim Neuzeichnen von Komponenten des Formulars, ist ein Bewusstsein für die genaue Reihenfolge, in der Ereignisse zur Laufzeit ausgelöst werden, geboten. Dieses Thema enthält Details zur Reihenfolge von Ereignissen im Verlauf einiger wichtiger Phasen der Lebensdauer von Anwendungen und Steuerelementen. Spezifische Details über die Reihenfolge von Mauseingabeereignissen finden Sie unter [Mausereignisse in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md). Einen Überblick über die Ereignisse in Windows Forms finden Sie unter [Ereignisübersicht](../../../docs/framework/winforms/events-overview-windows-forms.md). Ausführliche Informationen zur Zusammensetzung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
## <a name="application-startup-and-shutdown-events"></a>Ereignisse beim Starten und Herunterfahren von Anwendungen  
 Die Klassen <xref:System.Windows.Forms.Form> und <xref:System.Windows.Forms.Control> stellen einen Satz von Ereignissen bereit, die sich auf das Starten und Herunterfahren von Anwendungen beziehen. Beim Starten einer Windows Forms-Anwendung werden die Startereignisse des Hauptformulars in der folgenden Reihenfolge ausgelöst:  
  
-   <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 Beim Schließen einer Windows Forms-Anwendung werden die Ereignisse des Hauptformulars zum Herunterfahren in der folgenden Reihenfolge ausgelöst:  
  
-   <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 Das <xref:System.Windows.Forms.Application.ApplicationExit>-Ereignis der <xref:System.Windows.Forms.Application>-Klasse wird nach den Ereignissen des Hauptformulars zum Herunterfahren ausgelöst.  
  
> [!NOTE]
>  Visual Basic 2005 stellt zusätzliche Anwendungsereignisse bereit, z. B. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.  
  
## <a name="focus-and-validation-events"></a>Fokusereignisse und Validierungsereignisse  
 Wenn Sie den Fokus über die Tastatur ändern (TAB, UMSCHALT+TAB usw.), indem Sie die Methoden <xref:System.Windows.Forms.Control.Select%2A> oder <xref:System.Windows.Forms.Control.SelectNextControl%2A> aufrufen oder die <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A>-Eigenschaft auf das aktuelle Formular festlegen, treten die Fokusereignisse der <xref:System.Windows.Forms.Control>-Klasse in der folgenden Reihenfolge auf:  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
 Wenn Sie den Fokus über die Maus oder durch Aufrufen der <xref:System.Windows.Forms.Control.Focus%2A>-Methode ändern, treten die Fokusereignisse der <xref:System.Windows.Forms.Control>-Klasse in der folgenden Reihenfolge auf:  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
