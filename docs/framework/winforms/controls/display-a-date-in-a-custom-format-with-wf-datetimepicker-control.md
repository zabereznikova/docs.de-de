---
title: 'Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 0c454580c6f3aa1fadb6e98d2ee715da948364b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192991"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="61907-102">Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61907-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="61907-103">Die Windows-Formulare <xref:System.Windows.Forms.DateTimePicker> Control bietet Ihnen die Flexibilität bei der Formatierung der Anzeige von Datumsangaben und Uhrzeiten in das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61907-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="61907-104">Die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft ermöglicht Ihnen die Auswahl aus vordefinierten Formaten, aufgeführt der <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="61907-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="61907-105">Wenn keines dieser für Ihre Zwecke angemessen ist, können Sie erstellen Ihre eigenen Formatstil Formatzeichen in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="61907-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="61907-106">Um ein benutzerdefiniertes Format anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="61907-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="61907-107">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A> -Eigenschaft auf `DateTimePickerFormat.Custom`fest.</span><span class="sxs-lookup"><span data-stu-id="61907-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="61907-108">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft an eine Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="61907-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="61907-109">Hinzufügen von Text zu den formatierten Wert</span><span class="sxs-lookup"><span data-stu-id="61907-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="61907-110">Einfache Anführungszeichen verwenden, um alle Zeichen, die nicht Formatzeichen wie "M" oder Trennzeichen wie ist ":".</span><span class="sxs-lookup"><span data-stu-id="61907-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="61907-111">Die Formatzeichenfolge unten zeigt z. B. das aktuelle Datum im Format "heute ist: 05:30:31 Freitag März 02, 2012" in der Kultur Englisch (USA).</span><span class="sxs-lookup"><span data-stu-id="61907-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="61907-112">Abhängig von der kultureinstellung, darf keine Zeichen, die nicht in einfache Anführungszeichen eingeschlossen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="61907-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="61907-113">Die Formatzeichenfolge, die oben genannten zeigt z. B. das aktuelle Datum im Format "heute ist: 05:30:31 Freitag März 02, 2012" in der Kultur Englisch (USA).</span><span class="sxs-lookup"><span data-stu-id="61907-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="61907-114">Beachten Sie, dass es sich bei der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da sie ein Trennzeichen sein, wie es in "hh: mm:" ist nicht vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="61907-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="61907-115">In einer anderen Kultur, scheinen sich das Format als "aktuell sind: 05.30.31 Freitag März 02, 2012".</span><span class="sxs-lookup"><span data-stu-id="61907-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61907-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61907-116">See also</span></span>

- [<span data-ttu-id="61907-117">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="61907-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="61907-118">Vorgehensweise: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61907-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
