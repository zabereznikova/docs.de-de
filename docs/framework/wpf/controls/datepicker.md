---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460352"
---
# <a name="datepicker"></a>DatePicker
Das <xref:System.Windows.Controls.DatePicker> Steuerelement ermöglicht es dem Benutzer, ein Datum auszuwählen, indem es entweder in ein Textfeld eingegeben oder mithilfe eines Dropdown <xref:System.Windows.Controls.Calendar> Steuer Elements verwendet wird.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.DatePicker>.  
  
 ![DatePicker-Steuerelement](./media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker-Steuerelement  
  
 Viele der Eigenschaften eines <xref:System.Windows.Controls.DatePicker> Steuer Elements dienen zum Verwalten der integrierten <xref:System.Windows.Controls.Calendar>und funktionieren identisch mit der entsprechenden Eigenschaft in <xref:System.Windows.Controls.Calendar>. Insbesondere die Eigenschaften <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>und <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> funktionieren identisch mit ihren <xref:System.Windows.Controls.Calendar> Entsprechungen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.Calendar>.  
  
 Benutzer können ein Datum direkt in ein Textfeld eingeben, das die <xref:System.Windows.Controls.DatePicker.Text%2A>-Eigenschaft festlegt. Wenn das <xref:System.Windows.Controls.DatePicker> die eingegebene Zeichenfolge nicht in ein gültiges Datum konvertieren kann, wird das <xref:System.Windows.Controls.DatePicker.DateValidationError> Ereignis ausgelöst. Standardmäßig verursacht dies eine Ausnahme, aber ein Ereignishandler für <xref:System.Windows.Controls.DatePicker.DateValidationError> kann die <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A>-Eigenschaft auf `false` festlegen und verhindern, dass eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch

- [Steuerelemente](index.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
