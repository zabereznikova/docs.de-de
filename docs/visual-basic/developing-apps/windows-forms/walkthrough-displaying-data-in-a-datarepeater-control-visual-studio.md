---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231507"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="ae07f-102">Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ae07f-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="ae07f-103">Diese exemplarische Vorgehensweise enthält ein grundlegendes Szenario von Anfang bis zum Ende der Anzeige von gebundenen Daten in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ae07f-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="ae07f-104">Vorbereitungsmaßnahme</span><span class="sxs-lookup"><span data-stu-id="ae07f-104">Prerequisite</span></span>  
 <span data-ttu-id="ae07f-105">Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="ae07f-106">Wenn Sie diese Datenbank nicht auf Ihrem Computer verfügen, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="ae07f-107">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="ae07f-107">For instructions, see [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="ae07f-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ae07f-108">Overview</span></span>  
 <span data-ttu-id="ae07f-109">Der erste Teil dieser exemplarischen Vorgehensweise besteht aus vier Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="ae07f-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="ae07f-110">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="ae07f-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="ae07f-111">Hinzufügen eines <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="ae07f-112">Erstellen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ae07f-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="ae07f-113">Hinzufügen datengebundener Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ae07f-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="ae07f-114">Erstellen einer DataRepeater-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="ae07f-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="ae07f-115">Im ersten Schritt erstellen Sie ein Projekt und eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ae07f-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="ae07f-116">So erstellen Sie eine DataRepeater-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="ae07f-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="ae07f-117">Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="ae07f-118">Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="ae07f-119">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="ae07f-120">Geben Sie im Feld **Name** `DataRepeaterApp`ein.</span><span class="sxs-lookup"><span data-stu-id="ae07f-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="ae07f-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="ae07f-122">Der Windows Forms Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ae07f-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="ae07f-123">Öffnen Sie das Formular im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="ae07f-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="ae07f-124">Legen Sie im **Eigenschaften** -Fenster die Eigenschaft **Größe** auf `800, 700`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="ae07f-125">Hinzufügen eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="ae07f-126">In diesem Schritt fügen Sie dem Formular ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae07f-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="ae07f-127">So fügen Sie ein DataRepeater-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="ae07f-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="ae07f-128">Klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="ae07f-129">Die **Toolbox** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ae07f-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="ae07f-130">Wählen Sie die Registerkarte **Visual Basic PowerPacks** aus.</span><span class="sxs-lookup"><span data-stu-id="ae07f-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="ae07f-131">Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement auf **Form1**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="ae07f-132">Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `0, 25`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="ae07f-133">Legen Sie für die **Größe** -Eigenschaft den Wert `460, 600`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="ae07f-134">Hinzufügen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ae07f-134">Adding a Data Source</span></span>  
 <span data-ttu-id="ae07f-135">In diesem Schritt fügen Sie eine Datenquelle für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae07f-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="ae07f-136">So fügen Sie eine Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="ae07f-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="ae07f-137">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="ae07f-138">Klicken Sie im **Datenquellenfenster** auf **Neue Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="ae07f-139">Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ae07f-140">Führen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ae07f-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="ae07f-141">Wenn in der Dropdownliste eine Datenverbindung zur Beispieldatenbank Northwind verfügbar ist, klicken Sie auf diese.</span><span class="sxs-lookup"><span data-stu-id="ae07f-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="ae07f-142">- oder - </span><span class="sxs-lookup"><span data-stu-id="ae07f-142">-or-</span></span>  
  
    -   <span data-ttu-id="ae07f-143">Klicken Sie auf **Neue Verbindung** , um eine neue Datenverbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae07f-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="ae07f-144">Weitere Informationen finden Sie unter [neue Verbindungen hinzufügen](/visualstudio/data-tools/add-new-connections).</span><span class="sxs-lookup"><span data-stu-id="ae07f-144">For more information, see [Add new connections](/visualstudio/data-tools/add-new-connections).</span></span>  
  
5.  <span data-ttu-id="ae07f-145">Sollte für die Datenbank ein Kennwort erforderlich sein, wählen Sie die Option für die Einbeziehung vertraulicher Daten aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae07f-146">Wenn ein Dialogfeld angezeigt wird, wählen Sie **Ja** , um die Datei im Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ae07f-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="ae07f-147">Klicken Sie auf der Seite **Verbindungszeichenfolge in der Programmkonfigurationsdatei speichern** auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="ae07f-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="ae07f-148">Erweitern Sie auf der Seite **Datenbankobjekte auswählen** den Knoten **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="ae07f-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="ae07f-149">Aktivieren Sie die Kontrollkästchen für die Tabellen **Customers** und **Orders** , und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="ae07f-150">**NorthwindDataSet** wird dem Projekt hinzugefügt, und die Tabellen **Customers** und **Orders** werden im **Datenquellenfenster** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="ae07f-151">Hinzufügen datengebundener Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ae07f-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="ae07f-152">In diesem Schritt fügen Sie dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>datengebundene Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae07f-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="ae07f-153">So fügen Sie datengebundene Steuerelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="ae07f-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="ae07f-154">Wählen Sie im **Datenquellenfenster** den obersten Knoten für die **Customers** -Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="ae07f-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="ae07f-155">Ändern Sie den Ablagetyp für die Tabelle in **Details** , indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="ae07f-156">Wählen Sie den Tabellenknoten **Customers** aus, und ziehen Sie ihn in den Elementvorlagenbereich (oberer Bereich) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ae07f-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ae07f-157">Dem Formular wird ein <xref:System.Windows.Forms.BindingNavigator> -Steuerelement hinzugefügt, und die Komponenten **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**und **CustomersBindingNavigator** werden der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="ae07f-158">Wählen Sie alle Felder und ihre zugeordneten Bezeichnungen aus, und positionieren Sie sie am linken Rand des Elementvorlagenbereichs.</span><span class="sxs-lookup"><span data-stu-id="ae07f-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="ae07f-159">Wählen Sie die letzten fünf Felder (**Region**, **Postal Code**, **Country**, **Phone**und **Fax**) und ihre zugeordneten Bezeichnungen aus, und verschieben Sie sie nach oben rechts neben die ersten sechs Felder.</span><span class="sxs-lookup"><span data-stu-id="ae07f-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="ae07f-160">Wählen Sie die Elementvorlage (oberer Bereich des Steuerelements) aus.</span><span class="sxs-lookup"><span data-stu-id="ae07f-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="ae07f-161">Legen Sie im Eigenschaftenfenster die Eigenschaft **Größe** auf `427, 170`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="ae07f-162">An diesem Punkt haben Sie eine funktionierende Anwendung, die eine sich wiederholende Liste von Kunden anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="ae07f-163">Drücken Sie F5, um die Anwendung auszuführen, die Daten zu ändern und Kundendatensätze hinzuzufügen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="ae07f-164">Im nächsten optionalen Schritt erfahren Sie, wie Sie das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement anpassen können.</span><span class="sxs-lookup"><span data-stu-id="ae07f-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="ae07f-165">Nächste Schritte (optional)</span><span class="sxs-lookup"><span data-stu-id="ae07f-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="ae07f-166">Dieser Teil der exemplarischen Vorgehensweise besteht aus vier optionalen Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="ae07f-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="ae07f-167">Ändern der Darstellung des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="ae07f-168">Verhindern, dass Benutzer Datensätze hinzufügen oder löschen</span><span class="sxs-lookup"><span data-stu-id="ae07f-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="ae07f-169">Hinzufügen einer Suchfunktion zum <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="ae07f-170">Hinzufügen einer Master- und Detailtabelle zum <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="ae07f-171">Ändern der Darstellung des DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="ae07f-172">In diesem optionalen Schritt ändern Sie die `BackColor` des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="ae07f-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="ae07f-173">Sie fügen auch Code hinzu, um Zeilen in unterschiedlichen Farben anzuzeigen und die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ae07f-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="ae07f-174">So ändern Sie die Darstellung des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="ae07f-175">Wählen Sie im Windows Forms-Designer den Hauptbereich (unten) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ae07f-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="ae07f-176">Legen Sie im Eigenschaftenfenster die Eigenschaft `BackColor` auf „White“ fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="ae07f-177">Doppelklicken Sie auf den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="ae07f-178">Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="ae07f-179">Fügen Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler den folgenden Code hinzu, um die `BackColor`abzuwechseln:</span><span class="sxs-lookup"><span data-stu-id="ae07f-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="ae07f-180">Fügen Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler den folgenden Code hinzu, um die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ae07f-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="ae07f-181">Drücken Sie F5, um die Anwendung auszuführen und die Anpassungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="ae07f-182">Verhindern, dass Benutzer Datensätze hinzufügen oder löschen</span><span class="sxs-lookup"><span data-stu-id="ae07f-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="ae07f-183">In diesem optionalen Schritt fügen Sie Code hinzu, der verhindert, dass Benutzer Datensätze im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzufügen oder löschen kann.</span><span class="sxs-lookup"><span data-stu-id="ae07f-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="ae07f-184">So verhindern Sie, dass Benutzer Datensätze hinzufügt oder löscht</span><span class="sxs-lookup"><span data-stu-id="ae07f-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="ae07f-185">Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="ae07f-186">Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="ae07f-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="ae07f-187">Klicken Sie in der Dropdownliste „Klassenname“ auf **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="ae07f-188">Klicken Sie in der Dropdownliste „Methodenname“ auf **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="ae07f-189">Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="ae07f-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="ae07f-190">Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae07f-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="ae07f-191">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-191">Press F5 to run the application.</span></span> <span data-ttu-id="ae07f-192">Beachten Sie, dass die **DeleteItem** -Schaltfläche deaktiviert ist und dass Sie keine Elemente durch Drücken der ENTF-Taste löschen können.</span><span class="sxs-lookup"><span data-stu-id="ae07f-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="ae07f-193">Hinzufügen einer Suchfunktion zum DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="ae07f-194">In diesem optionalen Schritt implementieren Sie eine Funktion zum Suchen nach einem Wert im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ae07f-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="ae07f-195">Wenn die Suchzeichenfolge gefunden wird, wählt das Steuerelement das Element aus, das den Wert enthält, und führt einen Bildlauf zum Element durch.</span><span class="sxs-lookup"><span data-stu-id="ae07f-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="ae07f-196">So fügen Sie eine Suchfunktion hinzu</span><span class="sxs-lookup"><span data-stu-id="ae07f-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="ae07f-197">Ziehen Sie ein <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="ae07f-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ae07f-198">Positionieren Sie es unter dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ae07f-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="ae07f-199">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="ae07f-200">Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="ae07f-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="ae07f-201">Positionieren Sie es unter dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ae07f-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="ae07f-202">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="ae07f-203">Ändern Sie die **Text** -Eigenschaft in **Search**.</span><span class="sxs-lookup"><span data-stu-id="ae07f-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="ae07f-204">Doppelklicken Sie auf das <xref:System.Windows.Forms.Button> -Steuerelement, um den Code-Editor zu öffnen, und fügen Sie dem `SearchButton_Click` -Ereignishandler den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="ae07f-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="ae07f-205">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-205">Press F5 to run the application.</span></span> <span data-ttu-id="ae07f-206">Geben Sie eine Kunden-ID in **SearchTextBox** ein, und klicken Sie auf die Schaltfläche **Search** .</span><span class="sxs-lookup"><span data-stu-id="ae07f-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="ae07f-207">Hinzufügen einer Master- und Detailtabelle zum DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ae07f-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="ae07f-208">In diesem optionalen Schritt fügen Sie ein zweites <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu, um verbundene Aufträge für jeden Kunden anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="ae07f-209">So fügen Sie eine Master- und Detailtabelle hinzu</span><span class="sxs-lookup"><span data-stu-id="ae07f-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="ae07f-210">Ziehen Sie das zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="ae07f-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="ae07f-211">Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `465, 25`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="ae07f-212">Legen Sie für die **Größe** -Eigenschaft den Wert `315, 600`fest.</span><span class="sxs-lookup"><span data-stu-id="ae07f-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="ae07f-213">Erweitern Sie im **Datenquellenfenster** den Tabellenknoten **Customers** , und wählen Sie den Detailknoten für die Tabelle **Orders** aus.</span><span class="sxs-lookup"><span data-stu-id="ae07f-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="ae07f-214">Ändern Sie den Ablagetyp für die **Orders** -Tabelle in „Details“, indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="ae07f-215">Ziehen Sie den Tabellenknoten **Orders** in den Elementvorlagenbereich (oberer Bereich) des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ae07f-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ae07f-216">Eine **OrdersBindingSource** -Komponente und eine **OrdersTableAdapter** -Komponente werden der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="ae07f-217">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ae07f-217">Press F5 to run the application.</span></span> <span data-ttu-id="ae07f-218">Wenn Sie jeden Kunden im ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement auswählen, werden die Aufträge für diesen Kunden im zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae07f-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae07f-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae07f-219">See Also</span></span>  
 [<span data-ttu-id="ae07f-220">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-221">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-222">Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-223">Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-224">Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-225">Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-226">Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ae07f-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="ae07f-227">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ae07f-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ae07f-228">Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen</span><span class="sxs-lookup"><span data-stu-id="ae07f-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="ae07f-229">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ae07f-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
