---
title: "Vorgehensweise: Ändern der MonthCalendar-Steuerelement in Windows Forms &#39; s Darstellung"
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
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9c401532fa7a5f09462cf12084f32bca3f721cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a><span data-ttu-id="eaea7-102">Vorgehensweise: Ändern der MonthCalendar-Steuerelement in Windows Forms &#39; s Darstellung</span><span class="sxs-lookup"><span data-stu-id="eaea7-102">How to: Change the Windows Forms MonthCalendar Control&#39;s Appearance</span></span>
<span data-ttu-id="eaea7-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es Ihnen, zum Anpassen der Darstellung des Kalenders in vielerlei Hinsicht.</span><span class="sxs-lookup"><span data-stu-id="eaea7-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="eaea7-104">Sie können z. B. das Farbschema festlegen und Wochennummern und das aktuelle Datum ein- oder ausgeblendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eaea7-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="eaea7-105">So ändern Sie den Monatskalender Farbschema</span><span class="sxs-lookup"><span data-stu-id="eaea7-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="eaea7-106">Legen Sie Eigenschaften wie z. B. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaea7-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="eaea7-107">Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Tage der Woche.</span><span class="sxs-lookup"><span data-stu-id="eaea7-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="eaea7-108">Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaft bestimmt die Farbe der Datumsangaben, die vor und nach der angezeigten oder mehrere Monate.</span><span class="sxs-lookup"><span data-stu-id="eaea7-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="eaea7-109">Beginnen mit Windows Vista und je nach das Design, wird durch Festlegen einiger Eigenschaften möglicherweise nicht die Darstellung des Kalenders ändern.</span><span class="sxs-lookup"><span data-stu-id="eaea7-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="eaea7-110">Wenn Windows Aero Design verwenden festgelegt ist, z. B. durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaften hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="eaea7-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="eaea7-111">Dies ist, da eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, die zur Laufzeit aus dem aktuellen Design des Betriebssystems abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="eaea7-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="eaea7-112">Wenn Sie diese Eigenschaften verwenden und die frühere Version des Kalenders aktivieren möchten, können Sie visuelle Stile für die Anwendung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eaea7-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="eaea7-113">Deaktivieren von visuellen Stilen beeinträchtigt das Aussehen und Verhalten anderer Steuerelemente in Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eaea7-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="eaea7-114">Um visuelle Stile in Visual Basic zu deaktivieren, öffnen Sie den Projekt-Designer, und deaktivieren Sie die **XP aktiviert visuelle Stile** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="eaea7-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="eaea7-115">Um visuelle Stile in c# zu deaktivieren, öffnen Sie die Datei "Program.cs", und kommentieren Sie `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="eaea7-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="eaea7-116">Weitere Informationen zu visuellen Stilen finden Sie unter [Vorgehensweise: Aktivieren Sie visuelle Stile in Windows XP](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span><span class="sxs-lookup"><span data-stu-id="eaea7-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="eaea7-117">Das aktuelle Datum am unteren Rand des Steuerelements anzeigen</span><span class="sxs-lookup"><span data-stu-id="eaea7-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="eaea7-118">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="eaea7-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="eaea7-119">Das folgende Beispiel schaltet zwischen der Anzeige und das Auslassen des heutigen Datums, wenn das Formular doppelgeklickt wird.</span><span class="sxs-lookup"><span data-stu-id="eaea7-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="eaea7-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor der Form ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="eaea7-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="eaea7-121">Wochennummern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eaea7-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="eaea7-122">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="eaea7-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="eaea7-123">Sie können diese Eigenschaft im Code oder im Eigenschaftenfenster festlegen.</span><span class="sxs-lookup"><span data-stu-id="eaea7-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="eaea7-124">Wochennummern angezeigt werden, in einer separaten Spalte auf der linken Seite des ersten Tages der Woche.</span><span class="sxs-lookup"><span data-stu-id="eaea7-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eaea7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaea7-125">See Also</span></span>  
 [<span data-ttu-id="eaea7-126">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eaea7-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="eaea7-127">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eaea7-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="eaea7-128">Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eaea7-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [<span data-ttu-id="eaea7-129">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eaea7-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
