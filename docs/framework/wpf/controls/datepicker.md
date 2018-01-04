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
# <a name="datepicker"></a><span data-ttu-id="ec1ac-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="ec1ac-102">DatePicker</span></span>
<span data-ttu-id="ec1ac-103">Die <xref:System.Windows.Controls.DatePicker> -Steuerelement ermöglicht dem Benutzer ein Datum durch Eingabe in einem Textfeld oder mithilfe einer Dropdownliste auswählen <xref:System.Windows.Controls.Calendar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="ec1ac-104">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="ec1ac-105">![DatePicker-Steuerelement](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="ec1ac-105">![DatePicker control](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="ec1ac-106">DatePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ec1ac-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="ec1ac-107">Viele der eine <xref:System.Windows.Controls.DatePicker> Eigenschaften des Steuerelements werden für die Verwaltung von den integrierten <xref:System.Windows.Controls.Calendar>, und die Funktion identisch, die entsprechende Eigenschaft in <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="ec1ac-108">Insbesondere die <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, und <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> Eigenschaften funktionieren genauso wie ihre <xref:System.Windows.Controls.Calendar> Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="ec1ac-109">Weitere Informationen finden Sie unter <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="ec1ac-110">Benutzer können ein Datum eingeben, direkt in ein Textfeld, das festlegt der <xref:System.Windows.Controls.DatePicker.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="ec1ac-111">Wenn die <xref:System.Windows.Controls.DatePicker> die eingegebene Zeichenfolge kann nicht konvertiert werden, um ein gültiges Datum der <xref:System.Windows.Controls.DatePicker.DateValidationError> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="ec1ac-112">Standardmäßig Dies führt dazu, dass eine Ausnahme, jedoch einen Ereignishandler für <xref:System.Windows.Controls.DatePicker.DateValidationError> können festlegen, die <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> Eigenschaft `false` und zu verhindern, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ec1ac-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1ac-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec1ac-113">See Also</span></span>  
 [<span data-ttu-id="ec1ac-114">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ec1ac-114">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="ec1ac-115">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ec1ac-115">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
