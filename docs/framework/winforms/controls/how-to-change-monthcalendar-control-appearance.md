---
title: Darstellung des MonthCalendar-Steuer Elements ändern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: ded9059ede4ad03f637c0e697b880c41a9a8ba32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746657"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="dba77-102">Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dba77-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="dba77-103">Mit dem Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement können Sie die Darstellung des Kalenders in vielerlei Hinsicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="dba77-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="dba77-104">Beispielsweise können Sie das Farbschema festlegen und angeben, ob Wochen Nummern und das aktuelle Datum angezeigt oder ausgeblendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dba77-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="dba77-105">So ändern Sie das Farbschema des Monats Kalenders</span><span class="sxs-lookup"><span data-stu-id="dba77-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="dba77-106">Legen Sie Eigenschaften fest, z. b. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="dba77-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="dba77-107">Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>-Eigenschaft bestimmt auch die Schriftfarbe für die Wochentage.</span><span class="sxs-lookup"><span data-stu-id="dba77-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="dba77-108">Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>-Eigenschaft bestimmt die Farbe der Datumsangaben, die vorangestellt sind, und folgt den angezeigten Monaten oder Monaten.</span><span class="sxs-lookup"><span data-stu-id="dba77-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="dba77-109">Beginnend mit Windows Vista und abhängig vom Design wird durch das Festlegen einiger Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert.</span><span class="sxs-lookup"><span data-stu-id="dba77-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="dba77-110">Wenn Windows z. b. für die Verwendung des Aero-Designs festgelegt ist, hat das Festlegen der Eigenschaften <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> keinerlei Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="dba77-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="dba77-111">Dies liegt daran, dass eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, die zur Laufzeit aus dem aktuellen Betriebssystemdesign abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="dba77-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="dba77-112">Wenn Sie diese Eigenschaften verwenden und die frühere Version des Kalenders aktivieren möchten, können Sie visuelle Stile für die Anwendung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dba77-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="dba77-113">Das Deaktivieren von visuellen Stilen kann sich auf die Darstellung und das Verhalten anderer Steuerelemente in der Anwendung auswirken.</span><span class="sxs-lookup"><span data-stu-id="dba77-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="dba77-114">Um visuelle Stile in Visual Basic zu deaktivieren, öffnen Sie den Projekt-Designer, und deaktivieren Sie das Kontrollkästchen **Visual XP-Stile aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="dba77-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="dba77-115">Um visuelle Stile in C#zu deaktivieren, öffnen Sie Program.cs, und kommentieren Sie `Application.EnableVisualStyles();`aus.</span><span class="sxs-lookup"><span data-stu-id="dba77-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="dba77-116">Weitere Informationen zu visuellen Stilen finden Sie unter [Aktivieren von visuellen Stilen](/windows/desktop/controls/cookbook-overview).</span><span class="sxs-lookup"><span data-stu-id="dba77-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="dba77-117">So zeigen Sie das aktuelle Datum am unteren Rand des Steuer Elements an</span><span class="sxs-lookup"><span data-stu-id="dba77-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="dba77-118">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="dba77-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="dba77-119">Das folgende Beispiel wechselt zwischen dem anzeigen und Weglassen des aktuellen Datums, wenn auf das Formular Doppel geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="dba77-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     <span data-ttu-id="dba77-120">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="dba77-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="dba77-121">So zeigen Sie Wochen Nummern an</span><span class="sxs-lookup"><span data-stu-id="dba77-121">To display week numbers</span></span>  
  
- <span data-ttu-id="dba77-122">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="dba77-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="dba77-123">Sie können diese Eigenschaft entweder im Code oder im Eigenschaftenfenster festlegen.</span><span class="sxs-lookup"><span data-stu-id="dba77-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="dba77-124">Wochen Nummern werden in einer separaten Spalte auf der linken Seite des ersten Tags der Woche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dba77-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dba77-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dba77-125">See also</span></span>

- [<span data-ttu-id="dba77-126">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dba77-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="dba77-127">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dba77-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="dba77-128">Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dba77-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="dba77-129">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dba77-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
