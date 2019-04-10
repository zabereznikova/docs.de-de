---
title: 'Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: e7bc996c3d64c0ea3ac8fca5fef759ad309f2967
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336654"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="74d4d-102">Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="74d4d-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="74d4d-103">Das Erstellen von barrierefreien Anwendungen ist für Unternehmen von größter Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="74d4d-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="74d4d-104">Bei vielen staatlichen Stellen gibt es für den Kauf von Software Vorschriften hinsichtlich der Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="74d4d-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="74d4d-105">Das Certified for Windows-Logo beinhaltet Anforderungen zur Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="74d4d-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="74d4d-106">Allein in den USA gibt es etwa 30 Millionen Menschen, viele davon potenzielle Kunden, für die die Barrierefreiheit von Software maßgeblich ist.</span><span class="sxs-lookup"><span data-stu-id="74d4d-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="74d4d-107">In dieser exemplarischen Vorgehensweise werden die fünf Anforderungen zur Barrierefreiheit für das Certified for Windows-Logo erläutert.</span><span class="sxs-lookup"><span data-stu-id="74d4d-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="74d4d-108">Entsprechend diesen Anforderungen muss eine barrierefreie Anwendung folgende Forderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="74d4d-108">According to these requirements, an accessible application will:</span></span>  
  
-   <span data-ttu-id="74d4d-109">Unterstützung der Systemsteuerungseinstellungen für Größe, Farbe, Schriftart und Eingabe.</span><span class="sxs-lookup"><span data-stu-id="74d4d-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="74d4d-110">Wenn ein Benutzer die Einstellungen der Systemsteuerung ändert, wird die Größe der Menüleiste, der Titelleiste, der Ränder und der Statusleiste automatisch geändert.</span><span class="sxs-lookup"><span data-stu-id="74d4d-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="74d4d-111">In dieser Anwendung sind keine weiteren Änderungen an den Steuerelementen oder am Code erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74d4d-111">No additional changes to the controls or code are required in this application.</span></span>  
  
-   <span data-ttu-id="74d4d-112">Unterstützung für den Modus für hohe Kontraste.</span><span class="sxs-lookup"><span data-stu-id="74d4d-112">Support High Contrast mode.</span></span>  
  
-   <span data-ttu-id="74d4d-113">Bereitstellen von dokumentierten Tastaturzugriffen auf alle Features.</span><span class="sxs-lookup"><span data-stu-id="74d4d-113">Provide documented keyboard access to all features.</span></span>  
  
-   <span data-ttu-id="74d4d-114">Visuelle und programmgesteuerte Anzeige der Position des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="74d4d-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
-   <span data-ttu-id="74d4d-115">Vermeiden, dass wichtige Informationen ausschließlich akustisch übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="74d4d-116">Weitere Informationen finden Sie unter [Ressourcen für das Entwerfen von Anwendungen mit Barrierefreiheit](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="74d4d-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="74d4d-117">Informationen zur Unterstützung der verschiedenen Tastaturlayouts finden Sie unter [Empfehlungen für die Entwicklung weltweit einsatzfähiger Anwendungen](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="74d4d-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="74d4d-118">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="74d4d-118">Creating the Project</span></span>  
 <span data-ttu-id="74d4d-119">In dieser exemplarischen Vorgehensweise wird die Benutzeroberfläche für eine Anwendung erstellt, mit der Pizzabestellungen entgegengenommen werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="74d4d-120">Sie besteht aus einem <xref:System.Windows.Forms.TextBox>-Steuerelement für den Namen des Kunden, aus einer <xref:System.Windows.Forms.RadioButton>-Gruppe, um die Pizzagröße auszuwählen, aus einem <xref:System.Windows.Forms.CheckedListBox>-Steuerelement für die Auswahl des Belags, aus zwei Button-Steuerelementen, die mit "Bestellen" bzw. "Abbrechen" beschriftet sind, sowie aus einem Menü mit dem Befehl "Beenden".</span><span class="sxs-lookup"><span data-stu-id="74d4d-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="74d4d-121">Der Benutzer gibt den Namen des Kunden, die Größe der Pizza und die gewünschten Beläge ein.</span><span class="sxs-lookup"><span data-stu-id="74d4d-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="74d4d-122">Klickt der Benutzer auf die Schaltfläche "Bestellen", werden in einem Meldungsfeld eine Zusammenfassung der Bestellung sowie deren Preis angezeigt, und die Inhalte der Steuerelemente werden gelöscht, damit diese für die nächste Bestellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="74d4d-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="74d4d-123">Klickt der Benutzer auf die Schaltfläche "Abbrechen", werden die Inhalte der Steuerelemente gelöscht, damit diese für die nächste Bestellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="74d4d-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="74d4d-124">Klickt der Benutzer auf das Menüelement "Beenden", wird das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="74d4d-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="74d4d-125">Der Schwerpunkt dieser exemplarischen Vorgehensweise liegt nicht auf dem Code für das Bestellsystem, sondern auf der Barrierefreiheit der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="74d4d-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="74d4d-126">Die exemplarische Vorgehensweise veranschaulicht die Barrierefreiheitsfeatures von einigen häufig verwendeten Steuerelementen wie Schaltflächen, Optionsfelder, Textfelder und Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="74d4d-127">So beginnen Sie mit der Erstellung der Anwendung</span><span class="sxs-lookup"><span data-stu-id="74d4d-127">To begin making the application</span></span>  
  
-   <span data-ttu-id="74d4d-128">Erstellen Sie eine neue Windows-Anwendung in Visual Basic oder Visual C#.</span><span class="sxs-lookup"><span data-stu-id="74d4d-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="74d4d-129">Geben Sie dem Projekt den Namen **Pizzabestellung**.</span><span class="sxs-lookup"><span data-stu-id="74d4d-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="74d4d-130">(Weitere Informationen finden Sie unter [Erstellen neuer Projektmappen und Projekte](/visualstudio/ide/creating-solutions-and-projects).)</span><span class="sxs-lookup"><span data-stu-id="74d4d-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="74d4d-131">Hinzufügen der Steuerelemente zum Formular</span><span class="sxs-lookup"><span data-stu-id="74d4d-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="74d4d-132">Wenn Sie Steuerelemente zu einem Formular hinzufügen, sollten Sie die folgenden Richtlinien für eine barrierefreie Anwendung beachten:</span><span class="sxs-lookup"><span data-stu-id="74d4d-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
-   <span data-ttu-id="74d4d-133">Legen Sie für die Eigenschaften <xref:System.Windows.Forms.Control.AccessibleDescription%2A> und <xref:System.Windows.Forms.Control.AccessibleName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="74d4d-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="74d4d-134">In diesem Beispiel ist die Einstellung "Default" für <xref:System.Windows.Forms.Control.AccessibleRole%2A> ausreichend.</span><span class="sxs-lookup"><span data-stu-id="74d4d-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="74d4d-135">Weitere Informationen zu den Eigenschaften von Barrierefreiheit finden Sie unter [Informationen über die Barrierefreiheit für Steuerelemente in Windows Forms](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="74d4d-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
-   <span data-ttu-id="74d4d-136">Legen Sie den Schriftgrad auf 10 Punkt oder größer fest.</span><span class="sxs-lookup"><span data-stu-id="74d4d-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74d4d-137">Wenn Sie den Schriftgrad des Formulars auf 10 festlegen, wenn Sie beginnen, haben alle dem Formular anschließend hinzugefügten Steuerelemente ebenfalls den Schriftgrad 10.</span><span class="sxs-lookup"><span data-stu-id="74d4d-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
-   <span data-ttu-id="74d4d-138">Stellen Sie sicher, dass jedes Label-Steuerelement, das ein TextBox-Steuerelement beschreibt, dem TextBox-Steuerelement in der Aktivierreihenfolge direkt vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="74d4d-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
-   <span data-ttu-id="74d4d-139">Hinzufügen, mit dem Zeichen "&" eine Zugriffstaste der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft eines beliebigen Steuerelements, die der Benutzer navigieren kann soll.</span><span class="sxs-lookup"><span data-stu-id="74d4d-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
-   <span data-ttu-id="74d4d-140">Hinzufügen, mit dem Zeichen "&" eine Zugriffstaste der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft der Bezeichnung, die einem Steuerelement vorangestellt, die der Benutzer ggf. ist zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="74d4d-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="74d4d-141">Legen Sie <xref:System.Windows.Forms.Label.UseMnemonic%2A>-Eigenschaft der Bezeichnungen auf `true` fest, sodass der Fokus auf das nächste Steuerelement in der Aktivierreihenfolge festgelegt wird, wenn der Benutzer die Zugriffstaste drückt.</span><span class="sxs-lookup"><span data-stu-id="74d4d-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
-   <span data-ttu-id="74d4d-142">Fügen Sie allen Menüelementen Zugriffstasten hinzu.</span><span class="sxs-lookup"><span data-stu-id="74d4d-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="74d4d-143">So gestalten Sie eine Windows-Anwendung barrierefrei</span><span class="sxs-lookup"><span data-stu-id="74d4d-143">To make your Windows Application accessible</span></span>  
  
-   <span data-ttu-id="74d4d-144">Gehen Sie entsprechend der nachstehenden Beschreibung vor, um dem Formular die Steuerelemente hinzuzufügen und die Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="74d4d-145">Am Ende der Tabelle finden Sie ein Bild, das ein Modell für die Anordnung der Steuerelemente auf dem Formular zeigt.</span><span class="sxs-lookup"><span data-stu-id="74d4d-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="74d4d-146">Object</span><span class="sxs-lookup"><span data-stu-id="74d4d-146">Object</span></span>|<span data-ttu-id="74d4d-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="74d4d-147">Property</span></span>|<span data-ttu-id="74d4d-148">Wert</span><span class="sxs-lookup"><span data-stu-id="74d4d-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="74d4d-149">Form1</span><span class="sxs-lookup"><span data-stu-id="74d4d-149">Form1</span></span>|<span data-ttu-id="74d4d-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-150">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-151">Bestellformular</span><span class="sxs-lookup"><span data-stu-id="74d4d-151">Order form</span></span>|  
    ||<span data-ttu-id="74d4d-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-152">AccessibleName</span></span>|<span data-ttu-id="74d4d-153">Bestellformular</span><span class="sxs-lookup"><span data-stu-id="74d4d-153">Order form</span></span>|  
    ||<span data-ttu-id="74d4d-154">Schriftgrad</span><span class="sxs-lookup"><span data-stu-id="74d4d-154">Font Size</span></span>|<span data-ttu-id="74d4d-155">10</span><span class="sxs-lookup"><span data-stu-id="74d4d-155">10</span></span>|  
    ||<span data-ttu-id="74d4d-156">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-156">Text</span></span>|<span data-ttu-id="74d4d-157">Pizzabestellformular</span><span class="sxs-lookup"><span data-stu-id="74d4d-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="74d4d-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="74d4d-158">PictureBox</span></span>|<span data-ttu-id="74d4d-159">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-159">Name</span></span>|<span data-ttu-id="74d4d-160">Logo</span><span class="sxs-lookup"><span data-stu-id="74d4d-160">logo</span></span>|  
    ||<span data-ttu-id="74d4d-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-161">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-162">Ein Stück Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="74d4d-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-163">AccessibleName</span></span>|<span data-ttu-id="74d4d-164">Firmenlogo</span><span class="sxs-lookup"><span data-stu-id="74d4d-164">Company logo</span></span>|  
    ||<span data-ttu-id="74d4d-165">Bild</span><span class="sxs-lookup"><span data-stu-id="74d4d-165">Image</span></span>|<span data-ttu-id="74d4d-166">Ein Symbol oder eine Bitmap</span><span class="sxs-lookup"><span data-stu-id="74d4d-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="74d4d-167">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="74d4d-167">Label</span></span>|<span data-ttu-id="74d4d-168">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-168">Name</span></span>|<span data-ttu-id="74d4d-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="74d4d-169">companyLabel</span></span>|  
    ||<span data-ttu-id="74d4d-170">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-170">Text</span></span>|<span data-ttu-id="74d4d-171">Gute Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="74d4d-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-172">TabIndex</span></span>|<span data-ttu-id="74d4d-173">1</span><span class="sxs-lookup"><span data-stu-id="74d4d-173">1</span></span>|  
    ||<span data-ttu-id="74d4d-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-174">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-175">Firmenname</span><span class="sxs-lookup"><span data-stu-id="74d4d-175">Company name</span></span>|  
    ||<span data-ttu-id="74d4d-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-176">AccessibleName</span></span>|<span data-ttu-id="74d4d-177">Firmenname</span><span class="sxs-lookup"><span data-stu-id="74d4d-177">Company name</span></span>|  
    ||<span data-ttu-id="74d4d-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="74d4d-178">Backcolor</span></span>|<span data-ttu-id="74d4d-179">Blau</span><span class="sxs-lookup"><span data-stu-id="74d4d-179">Blue</span></span>|  
    ||<span data-ttu-id="74d4d-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="74d4d-180">Forecolor</span></span>|<span data-ttu-id="74d4d-181">Gelb</span><span class="sxs-lookup"><span data-stu-id="74d4d-181">Yellow</span></span>|  
    ||<span data-ttu-id="74d4d-182">Schriftgrad</span><span class="sxs-lookup"><span data-stu-id="74d4d-182">Font size</span></span>|<span data-ttu-id="74d4d-183">18</span><span class="sxs-lookup"><span data-stu-id="74d4d-183">18</span></span>|  
    |<span data-ttu-id="74d4d-184">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="74d4d-184">Label</span></span>|<span data-ttu-id="74d4d-185">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-185">Name</span></span>|<span data-ttu-id="74d4d-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="74d4d-186">customerLabel</span></span>|  
    ||<span data-ttu-id="74d4d-187">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-187">Text</span></span>|<span data-ttu-id="74d4d-188">&Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-188">&Name</span></span>|  
    ||<span data-ttu-id="74d4d-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-189">TabIndex</span></span>|<span data-ttu-id="74d4d-190">2</span><span class="sxs-lookup"><span data-stu-id="74d4d-190">2</span></span>|  
    ||<span data-ttu-id="74d4d-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-191">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-192">Kundennamenbez.</span><span class="sxs-lookup"><span data-stu-id="74d4d-192">Customer name label</span></span>|  
    ||<span data-ttu-id="74d4d-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-193">AccessibleName</span></span>|<span data-ttu-id="74d4d-194">Kundennamenbez.</span><span class="sxs-lookup"><span data-stu-id="74d4d-194">Customer name label</span></span>|  
    ||<span data-ttu-id="74d4d-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="74d4d-195">UseMnemonic</span></span>|<span data-ttu-id="74d4d-196">True</span><span class="sxs-lookup"><span data-stu-id="74d4d-196">True</span></span>|  
    |<span data-ttu-id="74d4d-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="74d4d-197">TextBox</span></span>|<span data-ttu-id="74d4d-198">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-198">Name</span></span>|<span data-ttu-id="74d4d-199">customerName</span><span class="sxs-lookup"><span data-stu-id="74d4d-199">customerName</span></span>|  
    ||<span data-ttu-id="74d4d-200">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-200">Text</span></span>|<span data-ttu-id="74d4d-201">(keine)</span><span class="sxs-lookup"><span data-stu-id="74d4d-201">(none)</span></span>|  
    ||<span data-ttu-id="74d4d-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-202">TabIndex</span></span>|<span data-ttu-id="74d4d-203">3</span><span class="sxs-lookup"><span data-stu-id="74d4d-203">3</span></span>|  
    ||<span data-ttu-id="74d4d-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-204">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-205">Kundenname</span><span class="sxs-lookup"><span data-stu-id="74d4d-205">Customer name</span></span>|  
    ||<span data-ttu-id="74d4d-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-206">AccessibleName</span></span>|<span data-ttu-id="74d4d-207">Kundenname</span><span class="sxs-lookup"><span data-stu-id="74d4d-207">Customer name</span></span>|  
    |<span data-ttu-id="74d4d-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="74d4d-208">GroupBox</span></span>|<span data-ttu-id="74d4d-209">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-209">Name</span></span>|<span data-ttu-id="74d4d-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="74d4d-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="74d4d-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-211">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-212">Mögliche Pizzagrößen</span><span class="sxs-lookup"><span data-stu-id="74d4d-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="74d4d-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-213">AccessibleName</span></span>|<span data-ttu-id="74d4d-214">Mögliche Pizzagrößen</span><span class="sxs-lookup"><span data-stu-id="74d4d-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="74d4d-215">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-215">Text</span></span>|<span data-ttu-id="74d4d-216">Pizzagröße</span><span class="sxs-lookup"><span data-stu-id="74d4d-216">Pizza size</span></span>|  
    ||<span data-ttu-id="74d4d-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-217">TabIndex</span></span>|<span data-ttu-id="74d4d-218">4</span><span class="sxs-lookup"><span data-stu-id="74d4d-218">4</span></span>|  
    |<span data-ttu-id="74d4d-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="74d4d-219">RadioButton</span></span>|<span data-ttu-id="74d4d-220">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-220">Name</span></span>|<span data-ttu-id="74d4d-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-221">smallPizza</span></span>|  
    ||<span data-ttu-id="74d4d-222">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-222">Text</span></span>|<span data-ttu-id="74d4d-223">&Klein 6,00 €</span><span class="sxs-lookup"><span data-stu-id="74d4d-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="74d4d-224">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="74d4d-224">Checked</span></span>|<span data-ttu-id="74d4d-225">True</span><span class="sxs-lookup"><span data-stu-id="74d4d-225">True</span></span>|  
    ||<span data-ttu-id="74d4d-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-226">TabIndex</span></span>|<span data-ttu-id="74d4d-227">0</span><span class="sxs-lookup"><span data-stu-id="74d4d-227">0</span></span>|  
    ||<span data-ttu-id="74d4d-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-228">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-229">Kleine Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-229">Small pizza</span></span>|  
    ||<span data-ttu-id="74d4d-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-230">AccessibleName</span></span>|<span data-ttu-id="74d4d-231">Kleine Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-231">Small pizza</span></span>|  
    |<span data-ttu-id="74d4d-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="74d4d-232">RadioButton</span></span>|<span data-ttu-id="74d4d-233">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-233">Name</span></span>|<span data-ttu-id="74d4d-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-234">largePizza</span></span>|  
    ||<span data-ttu-id="74d4d-235">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-235">Text</span></span>|<span data-ttu-id="74d4d-236">&Groß 10,00 €</span><span class="sxs-lookup"><span data-stu-id="74d4d-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="74d4d-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-237">TabIndex</span></span>|<span data-ttu-id="74d4d-238">1</span><span class="sxs-lookup"><span data-stu-id="74d4d-238">1</span></span>|  
    ||<span data-ttu-id="74d4d-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-239">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-240">Große Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-240">Large pizza</span></span>|  
    ||<span data-ttu-id="74d4d-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-241">AccessibleName</span></span>|<span data-ttu-id="74d4d-242">Große Pizza</span><span class="sxs-lookup"><span data-stu-id="74d4d-242">Large pizza</span></span>|  
    |<span data-ttu-id="74d4d-243">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="74d4d-243">Label</span></span>|<span data-ttu-id="74d4d-244">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-244">Name</span></span>|<span data-ttu-id="74d4d-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="74d4d-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="74d4d-246">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-246">Text</span></span>|<span data-ttu-id="74d4d-247">&Beläge (jeder 0,75 €)</span><span class="sxs-lookup"><span data-stu-id="74d4d-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="74d4d-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-248">TabIndex</span></span>|<span data-ttu-id="74d4d-249">5</span><span class="sxs-lookup"><span data-stu-id="74d4d-249">5</span></span>|  
    ||<span data-ttu-id="74d4d-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-250">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-251">Bezeichnung des Belags</span><span class="sxs-lookup"><span data-stu-id="74d4d-251">Toppings label</span></span>|  
    ||<span data-ttu-id="74d4d-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-252">AccessibleName</span></span>|<span data-ttu-id="74d4d-253">Bezeichnung des Belags</span><span class="sxs-lookup"><span data-stu-id="74d4d-253">Toppings label</span></span>|  
    ||<span data-ttu-id="74d4d-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="74d4d-254">UseMnemonic</span></span>|<span data-ttu-id="74d4d-255">True</span><span class="sxs-lookup"><span data-stu-id="74d4d-255">True</span></span>|  
    |<span data-ttu-id="74d4d-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="74d4d-256">CheckedListBox</span></span>|<span data-ttu-id="74d4d-257">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-257">Name</span></span>|<span data-ttu-id="74d4d-258">toppings</span><span class="sxs-lookup"><span data-stu-id="74d4d-258">toppings</span></span>|  
    ||<span data-ttu-id="74d4d-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-259">TabIndex</span></span>|<span data-ttu-id="74d4d-260">6</span><span class="sxs-lookup"><span data-stu-id="74d4d-260">6</span></span>|  
    ||<span data-ttu-id="74d4d-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-261">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-262">Mögliche Beläge</span><span class="sxs-lookup"><span data-stu-id="74d4d-262">Available toppings</span></span>|  
    ||<span data-ttu-id="74d4d-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-263">AccessibleName</span></span>|<span data-ttu-id="74d4d-264">Mögliche Beläge</span><span class="sxs-lookup"><span data-stu-id="74d4d-264">Available toppings</span></span>|  
    ||<span data-ttu-id="74d4d-265">Elemente</span><span class="sxs-lookup"><span data-stu-id="74d4d-265">Items</span></span>|<span data-ttu-id="74d4d-266">Peperoni, Salami, Champignons</span><span class="sxs-lookup"><span data-stu-id="74d4d-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="74d4d-267">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="74d4d-267">Button</span></span>|<span data-ttu-id="74d4d-268">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-268">Name</span></span>|<span data-ttu-id="74d4d-269">order</span><span class="sxs-lookup"><span data-stu-id="74d4d-269">order</span></span>|  
    ||<span data-ttu-id="74d4d-270">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-270">Text</span></span>|<span data-ttu-id="74d4d-271">Reihenf&olge</span><span class="sxs-lookup"><span data-stu-id="74d4d-271">&Order</span></span>|  
    ||<span data-ttu-id="74d4d-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-272">TabIndex</span></span>|<span data-ttu-id="74d4d-273">7</span><span class="sxs-lookup"><span data-stu-id="74d4d-273">7</span></span>|  
    ||<span data-ttu-id="74d4d-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-274">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-275">Gesamtbetrag der Bestellung ermitteln</span><span class="sxs-lookup"><span data-stu-id="74d4d-275">Total the order</span></span>|  
    ||<span data-ttu-id="74d4d-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-276">AccessibleName</span></span>|<span data-ttu-id="74d4d-277">Gesamtbetrag</span><span class="sxs-lookup"><span data-stu-id="74d4d-277">Total order</span></span>|  
    |<span data-ttu-id="74d4d-278">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="74d4d-278">Button</span></span>|<span data-ttu-id="74d4d-279">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-279">Name</span></span>|<span data-ttu-id="74d4d-280">cancel</span><span class="sxs-lookup"><span data-stu-id="74d4d-280">cancel</span></span>|  
    ||<span data-ttu-id="74d4d-281">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-281">Text</span></span>|<span data-ttu-id="74d4d-282">&Abbrechen</span><span class="sxs-lookup"><span data-stu-id="74d4d-282">&Cancel</span></span>|  
    ||<span data-ttu-id="74d4d-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="74d4d-283">TabIndex</span></span>|<span data-ttu-id="74d4d-284">8</span><span class="sxs-lookup"><span data-stu-id="74d4d-284">8</span></span>|  
    ||<span data-ttu-id="74d4d-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="74d4d-285">AccessibleDescription</span></span>|<span data-ttu-id="74d4d-286">Abbrechen der Bestellung</span><span class="sxs-lookup"><span data-stu-id="74d4d-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="74d4d-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="74d4d-287">AccessibleName</span></span>|<span data-ttu-id="74d4d-288">Bestellung abbrechen</span><span class="sxs-lookup"><span data-stu-id="74d4d-288">Cancel order</span></span>|  
    |<span data-ttu-id="74d4d-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="74d4d-289">MainMenu</span></span>|<span data-ttu-id="74d4d-290">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-290">Name</span></span>|<span data-ttu-id="74d4d-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="74d4d-291">theMainMenu</span></span>|  
    |<span data-ttu-id="74d4d-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="74d4d-292">MenuItem</span></span>|<span data-ttu-id="74d4d-293">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-293">Name</span></span>|<span data-ttu-id="74d4d-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="74d4d-294">fileCommands</span></span>|  
    ||<span data-ttu-id="74d4d-295">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-295">Text</span></span>|<span data-ttu-id="74d4d-296">&Datei</span><span class="sxs-lookup"><span data-stu-id="74d4d-296">&File</span></span>|  
    |<span data-ttu-id="74d4d-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="74d4d-297">MenuItem</span></span>|<span data-ttu-id="74d4d-298">Name</span><span class="sxs-lookup"><span data-stu-id="74d4d-298">Name</span></span>|<span data-ttu-id="74d4d-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="74d4d-299">exitApp</span></span>|  
    ||<span data-ttu-id="74d4d-300">Text</span><span class="sxs-lookup"><span data-stu-id="74d4d-300">Text</span></span>|<span data-ttu-id="74d4d-301">&Beenden</span><span class="sxs-lookup"><span data-stu-id="74d4d-301">E&xit</span></span>|
    
      <span data-ttu-id="74d4d-302">Das Formular sieht in etwa wie in der folgenden Abbildung:</span><span class="sxs-lookup"><span data-stu-id="74d4d-302">Your form will look something like the following image:</span></span>
    
      ![Die pizzabestellformular mit einer Namen im Textfeld "und" Größe "und" Beläge Auswahl.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)  

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="74d4d-304">Unterstützen des Modus für hohe Kontraste</span><span class="sxs-lookup"><span data-stu-id="74d4d-304">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="74d4d-305">Der Modus für hohe Kontraste ist eine Windows-Systemeinstellung, die die Lesbarkeit verbessert, indem kontrastreiche Farben und Schriftgrade verwendet werden, die für sehbehinderte Benutzer vorteilhaft sind.</span><span class="sxs-lookup"><span data-stu-id="74d4d-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="74d4d-306">Die <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> Eigenschaft wird bereitgestellt, um zu bestimmen, ob der Modus für hohe Kontraste festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="74d4d-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="74d4d-307">Wenn "SystemInformation.HighContrast" gleich `true` ist, muss die Anwendung wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="74d4d-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
-   <span data-ttu-id="74d4d-308">Sie zeigt alle Elemente der Benutzeroberfläche mit dem Systemfarbschema an.</span><span class="sxs-lookup"><span data-stu-id="74d4d-308">Display all user interface elements using the system color scheme</span></span>  
  
-   <span data-ttu-id="74d4d-309">Alle durch Farbe vermittelten Informationen müssen auch durch visuelle Hinweise oder durch Töne vermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="74d4d-310">Wenn beispielsweise bestimmte Listenelemente in roter Schrift hervorgehoben sind, können Sie diese auch noch fett formatieren, sodass der Benutzer einen nicht farblichen Hinweis hat, dass die Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="74d4d-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
-   <span data-ttu-id="74d4d-311">Hinter Text dürfen weder Symbole oder Muster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-311">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="74d4d-312">Die Anwendung muss beim Start die Einstellung von <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> überprüfen und danach auf das Systemereignis <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> reagieren.</span><span class="sxs-lookup"><span data-stu-id="74d4d-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="74d4d-313">Das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignis wird immer dann ausgelöst, wenn sich der Wert von <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> geändert hat.</span><span class="sxs-lookup"><span data-stu-id="74d4d-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="74d4d-314">In der vorliegenden Anwendung ist `lblCompanyName` das einzige Element, für das nicht die Systemeinstellungen für Farbe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="74d4d-315">Die <xref:System.Drawing.SystemColors> Klasse wird verwendet, um die farbeinstellungen der Bezeichnung in die vom Benutzer ausgewählten Systemfarben zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74d4d-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="74d4d-316">So aktivieren Sie den Modus für hohe Kontraste auf effektive Weise</span><span class="sxs-lookup"><span data-stu-id="74d4d-316">To enable High Contrast mode in an effective way</span></span>  
  
1. <span data-ttu-id="74d4d-317">Erstellen Sie eine Methode, mit der die Farben der Bezeichnung auf die Systemfarben festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-317">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2. <span data-ttu-id="74d4d-318">Rufen Sie die Prozedur `SetColorScheme` im Konstruktor des Formulars (`Public Sub New()`in Visual Basic und `public class Form1` in Visual C#) auf.</span><span class="sxs-lookup"><span data-stu-id="74d4d-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="74d4d-319">Damit Sie in Visual Basic auf den Konstruktor zugreifen können, müssen Sie den Bereich **Vom Windows Form-Designer generierter Code** erweitern.</span><span class="sxs-lookup"><span data-stu-id="74d4d-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3. <span data-ttu-id="74d4d-320">Erstellen Sie eine Ereignisprozedur mit der entsprechenden Signatur, um auf das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignis zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="74d4d-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4. <span data-ttu-id="74d4d-321">Fügen Sie dem Formularkonstruktor hinter dem Aufruf von `InitializeComponents` Code hinzu, der die Ereignisprozedur mit dem Systemereignis verknüpft.</span><span class="sxs-lookup"><span data-stu-id="74d4d-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="74d4d-322">Diese Methode ruft die `SetColorScheme`-Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="74d4d-322">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5. <span data-ttu-id="74d4d-323">Fügen Sie der <xref:System.Windows.Forms.Control.Dispose%2A>-Methode des Formulars vor dem Aufruf der <xref:System.Windows.Forms.Control.Dispose%2A>-Methode der Basisklasse Code hinzu, der das Ereignis freigibt, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="74d4d-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="74d4d-324">Damit Sie in Visual Basic auf die <xref:System.Windows.Forms.Control.Dispose%2A>-Methode zugreifen können, müssen Sie den Bereich "Vom Windows Form-Designer generierter Code" erweitern.</span><span class="sxs-lookup"><span data-stu-id="74d4d-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74d4d-325">Der Systemereigniscode führt getrennt von der Hauptanwendung einen Thread aus.</span><span class="sxs-lookup"><span data-stu-id="74d4d-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="74d4d-326">Wenn Sie das Ereignis nicht freigeben, wird auch nach dem Schließen des Programms weiterhin der Code ausgeführt, den Sie mit dem Ereignis verknüpft haben.</span><span class="sxs-lookup"><span data-stu-id="74d4d-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6. <span data-ttu-id="74d4d-327">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-327">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="74d4d-328">So vermitteln Sie wichtige Informationen anders als mit einer Tonfolge</span><span class="sxs-lookup"><span data-stu-id="74d4d-328">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="74d4d-329">In dieser Anwendung gibt es keine Informationen, die ausschließlich über eine Tonfolge vermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="74d4d-330">Wenn Sie Tonfolgen in Ihrer Anwendung verwenden, sollten Sie die Informationen auch auf andere Weise bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="74d4d-331">So stellen Sie Informationen auf andere Weise als über Tonfolgen bereit</span><span class="sxs-lookup"><span data-stu-id="74d4d-331">To supply information by some other means than sound</span></span>  
  
1. <span data-ttu-id="74d4d-332">Lassen Sie die Titelleiste mithilfe der Windows-API-Funktion "FlashWindow" blinken.</span><span class="sxs-lookup"><span data-stu-id="74d4d-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="74d4d-333">Ein Beispiel für das Aufrufen von Windows-API-Funktionen, finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="74d4d-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74d4d-334">Möglicherweise hat der Benutzer den Windows-Dienst "Darstellungsoptionen" aktiviert, der ebenfalls bewirkt, dass das Fenster blinkt, wenn Systemsounds über die integrierten Lautsprecher des Computers wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2. <span data-ttu-id="74d4d-335">Zeigen Sie die wichtigen Informationen in einem nicht modalen Fenster an, damit der Benutzer darauf reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="74d4d-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3. <span data-ttu-id="74d4d-336">Zeigen Sie ein Meldungsfeld an, das den Tastaturfokus erhält.</span><span class="sxs-lookup"><span data-stu-id="74d4d-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="74d4d-337">Vermeiden Sie diese Methode, wenn der Benutzer eine Eingabe vornimmt.</span><span class="sxs-lookup"><span data-stu-id="74d4d-337">Avoid this method when the user may be typing.</span></span>  
  
4. <span data-ttu-id="74d4d-338">Zeigen Sie eine Statusanzeige im Statusbereich der Taskleiste an.</span><span class="sxs-lookup"><span data-stu-id="74d4d-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="74d4d-339">Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="74d4d-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="74d4d-340">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="74d4d-340">Testing the Application</span></span>  
 <span data-ttu-id="74d4d-341">Bevor Sie die Anwendung bereitstellen, sollten Sie die implementierten Barrierefreiheitsfeatures testen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="74d4d-342">So testen Sie die Barrierefreiheitsfeatures</span><span class="sxs-lookup"><span data-stu-id="74d4d-342">To test accessibility features</span></span>  
  
1. <span data-ttu-id="74d4d-343">Um den Tastaturzugriff zu testen, ziehen Sie den Stecker des Mauskabels heraus, und navigieren Sie in der Benutzeroberfläche nur über die Tastatur zu jedem Feature.</span><span class="sxs-lookup"><span data-stu-id="74d4d-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="74d4d-344">Vergewissern Sie sich, dass alle Aufgaben über die Tastatur ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="74d4d-344">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2. <span data-ttu-id="74d4d-345">Um die Unterstützung für hohen Kontrast zu testen, wählen Sie in der Systemsteuerung das Symbol "Eingabehilfen" aus.</span><span class="sxs-lookup"><span data-stu-id="74d4d-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="74d4d-346">Klicken Sie auf die Registerkarte "Anzeige", und aktivieren Sie das Kontrollkästchen für die Verwendung von hohem Kontrast.</span><span class="sxs-lookup"><span data-stu-id="74d4d-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="74d4d-347">Navigieren Sie durch alle Elemente der Benutzeroberfläche, um sich zu vergewissern, dass die Farb- und Schriftartänderungen übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="74d4d-348">Stellen Sie außerdem sicher, dass hinter Text gezeichnete Symbole und Muster unterdrückt werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74d4d-349">In der Systemsteuerung von Windows NT 4 gibt es kein Symbol für Eingabehilfen (Barrierefreiheit).</span><span class="sxs-lookup"><span data-stu-id="74d4d-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="74d4d-350">Daher funktioniert diese Vorgehensweise zum Ändern der SystemInformation.HighContrast-Einstellung in Windows NT 4 nicht.</span><span class="sxs-lookup"><span data-stu-id="74d4d-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3. <span data-ttu-id="74d4d-351">Die Barrierefreiheit einer Anwendung kann außerdem mithilfe direkt verfügbarer Tools getestet werden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-351">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4. <span data-ttu-id="74d4d-352">Um die Verfügbarmachung des Tastaturfokus zu testen, führen Sie Bildschirmlupe aus.</span><span class="sxs-lookup"><span data-stu-id="74d4d-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="74d4d-353">(Um Bildschirmlupe zu öffnen, klicken Sie auf **Start**, zeigen Sie auf **Programm**e, zeigen Sie auf **Zubehör,** zeigen Sie auf **Barrierefreiheit**, und klicken Sie dann auf **Bildschirmlupe**).</span><span class="sxs-lookup"><span data-stu-id="74d4d-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="74d4d-354">Navigieren Sie in der Benutzeroberfläche, wobei Sie sowohl die TAB-Taste als auch die Maus verwenden.</span><span class="sxs-lookup"><span data-stu-id="74d4d-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="74d4d-355">Vergewissern Sie sich, dass die gesamte Navigation in **Bildschirmlupe** ordnungsgemäß nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="74d4d-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5. <span data-ttu-id="74d4d-356">Um die Verfügbarmachung der Bildschirmelemente zu testen, führen Sie Inspect aus, und verwenden Sie die Maus und die TAB-Taste, um jedes Element zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="74d4d-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="74d4d-357">Vergewissern Sie sich, dass die Informationen, die im Fenster "Inspect" in den Feldern "Name", "State", "Role", "Location" und "Value" angezeigt werden, für den Benutzer für jedes Objekt in der Benutzeroberfläche aussagekräftig sind.</span><span class="sxs-lookup"><span data-stu-id="74d4d-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
