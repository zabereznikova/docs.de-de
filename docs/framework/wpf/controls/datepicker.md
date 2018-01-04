---
title: DatePicker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2a1755ae076369661b2c9a7a2b744961cdb129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker"></a>DatePicker
Die <xref:System.Windows.Controls.DatePicker> -Steuerelement ermöglicht dem Benutzer ein Datum durch Eingabe in einem Textfeld oder mithilfe einer Dropdownliste auswählen <xref:System.Windows.Controls.Calendar> Steuerelement.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.DatePicker>.  
  
 ![DatePicker-Steuerelement](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker-Steuerelement  
  
 Viele der eine <xref:System.Windows.Controls.DatePicker> Eigenschaften des Steuerelements werden für die Verwaltung von den integrierten <xref:System.Windows.Controls.Calendar>, und die Funktion identisch, die entsprechende Eigenschaft in <xref:System.Windows.Controls.Calendar>. Insbesondere die <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, und <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> Eigenschaften funktionieren genauso wie ihre <xref:System.Windows.Controls.Calendar> Entsprechungen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.Calendar>.  
  
 Benutzer können ein Datum eingeben, direkt in ein Textfeld, das festlegt der <xref:System.Windows.Controls.DatePicker.Text%2A> Eigenschaft. Wenn die <xref:System.Windows.Controls.DatePicker> die eingegebene Zeichenfolge kann nicht konvertiert werden, um ein gültiges Datum der <xref:System.Windows.Controls.DatePicker.DateValidationError> Ereignis wird ausgelöst. Standardmäßig Dies führt dazu, dass eine Ausnahme, jedoch einen Ereignishandler für <xref:System.Windows.Controls.DatePicker.DateValidationError> können festlegen, die <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> Eigenschaft `false` und zu verhindern, dass eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
