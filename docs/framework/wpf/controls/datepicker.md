---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 555bf31b27ba233ffa54438077984b02b5e3084a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911981"
---
# <a name="datepicker"></a>DatePicker
Die <xref:System.Windows.Controls.DatePicker> Steuerelement ermöglicht dem Benutzer, wählen Sie ein Datum durch Eingabe in ein Textfeld oder ein Dropdownmenü mit <xref:System.Windows.Controls.Calendar> Steuerelement.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.DatePicker>.  
  
 ![DatePicker-Steuerelement](./media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker-Steuerelement  
  
 Viele der ein <xref:System.Windows.Controls.DatePicker> Eigenschaften des Steuerelements sind für die Verwaltung von den integrierten <xref:System.Windows.Controls.Calendar>, und werden genau wie die entsprechende Eigenschaft in <xref:System.Windows.Controls.Calendar>. Insbesondere die <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, und <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> Eigenschaften funktionieren genauso wie ihre <xref:System.Windows.Controls.Calendar> Entsprechungen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.Calendar>.  
  
 Benutzer können ein Datum eingeben, direkt in einem Textfeld, das festlegt der <xref:System.Windows.Controls.DatePicker.Text%2A> Eigenschaft. Wenn die <xref:System.Windows.Controls.DatePicker> die eingegebene Zeichenfolge kann nicht konvertiert werden, um ein gültiges Datum ist, die <xref:System.Windows.Controls.DatePicker.DateValidationError> Ereignis wird ausgelöst. Standardmäßig bewirkt diese eine Ausnahme aus, aber einen Ereignishandler für <xref:System.Windows.Controls.DatePicker.DateValidationError> können festlegen, die <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> Eigenschaft `false` und zu verhindern, dass eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch

- [Steuerelemente](index.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
