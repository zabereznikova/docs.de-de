---
title: 'Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 21fa6798c431b71d36c1909937ddad6bf5030782
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053091"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="9f785-102">Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f785-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="9f785-103">Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es Ihnen, zum Anpassen der Darstellung des Kalenders in vielerlei Hinsicht.</span><span class="sxs-lookup"><span data-stu-id="9f785-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="9f785-104">Sie können z. B. das Farbschema festlegen und anzeigen oder ausblenden Wochennummern und dem aktuellen Datum.</span><span class="sxs-lookup"><span data-stu-id="9f785-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="9f785-105">Der im Monatskalender Farbschema ändern</span><span class="sxs-lookup"><span data-stu-id="9f785-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="9f785-106">Legen Sie Eigenschaften wie z. B. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f785-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="9f785-107">Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Tage der Woche.</span><span class="sxs-lookup"><span data-stu-id="9f785-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="9f785-108">Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> -Eigenschaft bestimmt die Farbe der Datumsangaben, die vor und nach den angezeigten Monat oder Monaten.</span><span class="sxs-lookup"><span data-stu-id="9f785-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="9f785-109">Beginnen mit Windows Vista und das Design, wird durch Festlegen von einige Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert.</span><span class="sxs-lookup"><span data-stu-id="9f785-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="9f785-110">Wenn Windows festgelegt ist, verwenden Sie die Aero-Design, z. B. Festlegen der <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaften hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="9f785-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="9f785-111">Das liegt eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, das zur Laufzeit aus dem aktuellen Betriebssystem Design abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9f785-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="9f785-112">Wenn Sie diese Eigenschaften verwenden, und aktivieren Sie die frühere Version des Kalenders möchten, können Sie visuelle Stile für Ihre Anwendung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f785-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="9f785-113">Deaktivieren von visuellen Stilen kann die Darstellung und das Verhalten anderer Steuerelemente in Ihrer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="9f785-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="9f785-114">Klicken Sie zum Deaktivieren von visuellen Stilen in Visual Basic den Projekt-Designer zu öffnen, und deaktivieren Sie die **XP visual-Stile aktivieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="9f785-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="9f785-115">Klicken Sie zum Deaktivieren von visuellen Stilen in C#-Datei "Program.cs" öffnen, und kommentieren Sie `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="9f785-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="9f785-116">Weitere Informationen zu visuellen Stilen finden Sie unter [Aktivieren von visuellen Stilen](/windows/desktop/controls/cookbook-overview).</span><span class="sxs-lookup"><span data-stu-id="9f785-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="9f785-117">Das aktuelle Datum am unteren Rand des Steuerelements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f785-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="9f785-118">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="9f785-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="9f785-119">Das folgende Beispiel schaltet zwischen der Anzeige und das Auslassen des heutigen Datums, wenn das Formular doppelgeklickt wird.</span><span class="sxs-lookup"><span data-stu-id="9f785-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="9f785-120">(Visual C#, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9f785-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="9f785-121">Wochennummern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f785-121">To display week numbers</span></span>  
  
- <span data-ttu-id="9f785-122">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="9f785-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="9f785-123">Sie können diese Eigenschaft im Code oder im Fenster Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="9f785-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="9f785-124">Wochennummern angezeigt werden, in einer separaten Spalte auf der linken Seite des ersten Tages der Woche.</span><span class="sxs-lookup"><span data-stu-id="9f785-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f785-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f785-125">See also</span></span>

- [<span data-ttu-id="9f785-126">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f785-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="9f785-127">Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f785-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="9f785-128">Vorgehensweise: Anzeige bestimmte Tage im mit der Windows Bold Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f785-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="9f785-129">Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f785-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
