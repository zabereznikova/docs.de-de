---
title: Festlegen und Zurückgeben von Datumsangaben mit DateTimePicker-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 1e0aa58e98748ccde9411f0f4871adbae3a5f14d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747110"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="cb3be-102">Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb3be-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="cb3be-103">Die aktuell im <xref:System.Windows.Forms.DateTimePicker>-Steuerelement von Windows Forms ausgewählte Datumsangabe (Datum und Uhrzeit) ist durch die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cb3be-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="cb3be-104">Sie können die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft festlegen, bevor das Steuerelement angezeigt wird (z. B. zur Entwurfszeit oder im <xref:System.Windows.Forms.Form.Load>-Ereignis des Formulars), um zu bestimmen, welches Datum zunächst im Steuerelement ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="cb3be-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="cb3be-105">Standardmäßig wird die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft des Steuerelements auf das aktuelle Datum festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb3be-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="cb3be-106">Wenn Sie die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft des Steuerelements im Code ändern, wird das Steuerelement auf dem Formular automatisch entsprechend der neuen Einstellung aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cb3be-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="cb3be-107">Die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft gibt eine <xref:System.DateTime>-Struktur als ihren Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="cb3be-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="cb3be-108">Es gibt verschiedene Eigenschaften der <xref:System.DateTime>-Struktur, die bestimmte Informationen zum angezeigten Datum zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cb3be-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="cb3be-109">Mit diesen Eigenschaften können Werte nur zurückgegeben, aber nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cb3be-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
- <span data-ttu-id="cb3be-110">Für Datumswerte geben die Eigenschaften <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> und <xref:System.DateTime.Year%2A> Ganzzahlwerte für diese Zeiteinheiten des ausgewählten Datums zurück.</span><span class="sxs-lookup"><span data-stu-id="cb3be-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="cb3be-111">Die <xref:System.DateTime.DayOfWeek%2A>-Eigenschaft gibt einen Wert zurück, der den ausgewählten Wochentag angibt (mögliche Werte sind in der <xref:System.DayOfWeek>-Enumeration aufgelistet).</span><span class="sxs-lookup"><span data-stu-id="cb3be-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
- <span data-ttu-id="cb3be-112">Für Zeitwerte geben die Eigenschaften <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> und <xref:System.DateTime.Millisecond%2A> Ganzzahlwerte für diese Zeiteinheiten zurück.</span><span class="sxs-lookup"><span data-stu-id="cb3be-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="cb3be-113">Informationen zum Konfigurieren des Steuer Elements für die Anzeige von Zeiten finden Sie unter Gewusst [wie: Anzeigen der Zeit mit dem DateTimePicker-Steuer](how-to-display-time-with-the-datetimepicker-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="cb3be-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="cb3be-114">So legen Sie das Datum und die Uhrzeit für das Steuerelement fest</span><span class="sxs-lookup"><span data-stu-id="cb3be-114">To set the date and time value of the control</span></span>  
  
- <span data-ttu-id="cb3be-115">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft auf einen Datums- oder Uhrzeitwert fest.</span><span class="sxs-lookup"><span data-stu-id="cb3be-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="cb3be-116">So geben Sie den Datums- und den Uhrzeitwert zurück</span><span class="sxs-lookup"><span data-stu-id="cb3be-116">To return the date and time value</span></span>  
  
- <span data-ttu-id="cb3be-117">Rufen Sie die <xref:System.Windows.Forms.DateTimePicker.Text%2A>-Eigenschaft auf, um den gesamten Wert so zurückzugeben, wie er im Steuerelement formatiert ist, oder rufen Sie die entsprechende Methode der <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft auf, um einen Teil des Werts zurückzugeben</span><span class="sxs-lookup"><span data-stu-id="cb3be-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="cb3be-118">Verwenden Sie <xref:System.Windows.Forms.DateTimePicker.ToString%2A>, um die Informationen in eine Zeichenfolge zu konvertieren, die Benutzern angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb3be-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cb3be-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb3be-119">See also</span></span>

- [<span data-ttu-id="cb3be-120">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb3be-120">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="cb3be-121">Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb3be-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
