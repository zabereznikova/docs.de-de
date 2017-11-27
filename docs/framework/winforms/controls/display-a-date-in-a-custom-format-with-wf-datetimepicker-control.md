---
title: "Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b92fec7565aad2a881f714f9232eae10bf7633c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="a3c89-102">Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3c89-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="a3c89-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> Steuerelement bietet Ihnen die Flexibilität beim Formatieren der Anzeige von Datums- und Uhrzeitangaben im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a3c89-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="a3c89-104">Die <xref:System.Windows.Forms.DateTimePicker.Format%2A> -Eigenschaft können Sie in aufgeführten vordefinierten Formate aus der <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="a3c89-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="a3c89-105">Wenn keiner dieser für Ihre Zwecke angemessen ist, können Sie eigene Formatstil Formatieren von Zeichen in aufgeführt erstellen <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3c89-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="a3c89-106">Um ein benutzerdefiniertes Format anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a3c89-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="a3c89-107">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf `DateTimePickerFormat.Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="a3c89-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="a3c89-108">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft auf eine Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a3c89-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="a3c89-109">Der formatierte Wert Text hinzu</span><span class="sxs-lookup"><span data-stu-id="a3c89-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="a3c89-110">Verwenden Sie einfache Anführungszeichen zum Einschließen von einem beliebigen Zeichen, die nicht Formatzeichen wie "M" oder ein Trennzeichen wie ist ":".</span><span class="sxs-lookup"><span data-stu-id="a3c89-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="a3c89-111">Die Formatzeichenfolge unten zeigt z. B. das aktuelle Datum im Format "heutzutage: 05:30:31 Freitag 02 März 2012" in der englischen (USA) Kultur.</span><span class="sxs-lookup"><span data-stu-id="a3c89-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="a3c89-112">Abhängig von der kultureinstellung darf keine Zeichen, die nicht in einfache Anführungszeichen eingeschlossen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3c89-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="a3c89-113">Die Formatzeichenfolge, die oben genannten zeigt z. B. das aktuelle Datum im Format "heutzutage: 05:30:31 Freitag 02 März 2012" in der englischen (USA) Kultur.</span><span class="sxs-lookup"><span data-stu-id="a3c89-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="a3c89-114">Beachten Sie, dass es sich bei der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da sie nicht dazu gedacht ist ein Trennzeichen ist, wie diese in "hh" sind.</span><span class="sxs-lookup"><span data-stu-id="a3c89-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="a3c89-115">In einer anderen Kultur könnte das Format als angezeigt werden "heutzutage: 05.30.31 Freitag 02 März 2012".</span><span class="sxs-lookup"><span data-stu-id="a3c89-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3c89-116">See Also</span></span>  
 [<span data-ttu-id="a3c89-117">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a3c89-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="a3c89-118">Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3c89-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
