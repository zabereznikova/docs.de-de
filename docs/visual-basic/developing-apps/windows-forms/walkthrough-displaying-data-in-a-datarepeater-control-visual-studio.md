---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b795b8f3bb42aecdbdfade62f4943239fec6eac4
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="660e1-102">Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="660e1-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="660e1-103">Diese exemplarische Vorgehensweise enthält ein grundlegende Anfang-Ende-Szenario zum Anzeigen von gebundenen Daten in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="660e1-104">Vorbereitungsmaßnahme</span><span class="sxs-lookup"><span data-stu-id="660e1-104">Prerequisite</span></span>  
 <span data-ttu-id="660e1-105">Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.</span><span class="sxs-lookup"><span data-stu-id="660e1-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="660e1-106">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="660e1-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="660e1-107">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="660e1-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="660e1-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="660e1-108">Overview</span></span>  
 <span data-ttu-id="660e1-109">Der erste Teil dieser exemplarischen Vorgehensweise besteht aus vier Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="660e1-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="660e1-110">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="660e1-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="660e1-111">Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="660e1-112">Erstellen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="660e1-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="660e1-113">Hinzufügen datengebundener Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="660e1-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="660e1-114">Erstellen einer DataRepeater-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="660e1-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="660e1-115">Im ersten Schritt erstellen Sie ein Projekt und eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="660e1-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="660e1-116">So erstellen Sie eine DataRepeater-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="660e1-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="660e1-117">Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="660e1-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="660e1-118">Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="660e1-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="660e1-119">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="660e1-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="660e1-120">Geben Sie im Feld **Name** `DataRepeaterApp`ein.</span><span class="sxs-lookup"><span data-stu-id="660e1-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="660e1-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="660e1-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="660e1-122">Der Windows Forms Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="660e1-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="660e1-123">Öffnen Sie das Formular im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="660e1-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="660e1-124">Legen Sie im **Eigenschaften** -Fenster die Eigenschaft **Größe** auf `800, 700`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="660e1-125">Hinzufügen eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="660e1-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="660e1-126">In diesem Schritt fügen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement auf das Formular.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="660e1-127">So fügen Sie ein DataRepeater-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="660e1-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="660e1-128">Klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="660e1-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="660e1-129">Die **Toolbox** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="660e1-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="660e1-130">Wählen Sie die Registerkarte **Visual Basic PowerPacks** aus.</span><span class="sxs-lookup"><span data-stu-id="660e1-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="660e1-131">Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement auf **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="660e1-132">Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `0, 25`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="660e1-133">Legen Sie für die **Größe** -Eigenschaft den Wert `460, 600`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="660e1-134">Hinzufügen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="660e1-134">Adding a Data Source</span></span>  
 <span data-ttu-id="660e1-135">In diesem Schritt fügen Sie eine Datenquelle für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="660e1-136">So fügen Sie eine Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="660e1-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="660e1-137">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="660e1-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="660e1-138">Klicken Sie im **Datenquellenfenster** auf **Neue Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="660e1-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="660e1-139">Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="660e1-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="660e1-140">Führen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="660e1-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="660e1-141">Wenn in der Dropdownliste eine Datenverbindung zur Beispieldatenbank Northwind verfügbar ist, klicken Sie auf diese.</span><span class="sxs-lookup"><span data-stu-id="660e1-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="660e1-142">- oder -</span><span class="sxs-lookup"><span data-stu-id="660e1-142">-or-</span></span>  
  
    -   <span data-ttu-id="660e1-143">Klicken Sie auf **Neue Verbindung** , um eine neue Datenverbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="660e1-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="660e1-144">Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Verbindungen mit SQL Server-Datenbanken](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span><span class="sxs-lookup"><span data-stu-id="660e1-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="660e1-145">Sollte für die Datenbank ein Kennwort erforderlich sein, wählen Sie die Option für die Einbeziehung vertraulicher Daten aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="660e1-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="660e1-146">Wenn ein Dialogfeld angezeigt wird, wählen Sie **Ja** , um die Datei im Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="660e1-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="660e1-147">Klicken Sie auf der Seite **Verbindungszeichenfolge in der Programmkonfigurationsdatei speichern** auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="660e1-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="660e1-148">Erweitern Sie auf der Seite **Datenbankobjekte auswählen** den Knoten **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="660e1-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="660e1-149">Aktivieren Sie die Kontrollkästchen für die Tabellen **Customers** und **Orders** , und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="660e1-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="660e1-150">**NorthwindDataSet** wird dem Projekt hinzugefügt, und die Tabellen **Customers** und **Orders** werden im **Datenquellenfenster** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="660e1-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="660e1-151">Hinzufügen datengebundener Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="660e1-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="660e1-152">In diesem Schritt fügen Sie datengebundene Steuerelemente mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="660e1-153">So fügen Sie datengebundene Steuerelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="660e1-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="660e1-154">Wählen Sie im **Datenquellenfenster** den obersten Knoten für die **Customers** -Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="660e1-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="660e1-155">Ändern Sie den Ablagetyp für die Tabelle in **Details** , indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.</span><span class="sxs-lookup"><span data-stu-id="660e1-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="660e1-156">Wählen Sie die **Kunden** Knoten Tabelle, und ziehen Sie es auf den Elementvorlagenbereich (der obere Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="660e1-157">Ein <xref:System.Windows.Forms.BindingNavigator>Steuerelement wird dem Formular hinzugefügt und die **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, und **CustomersBindingNavigator** Komponenten werden auf der Komponentenleiste hinzugefügt.</xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="660e1-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="660e1-158">Wählen Sie alle Felder und ihre zugeordneten Bezeichnungen aus, und positionieren Sie sie am linken Rand des Elementvorlagenbereichs.</span><span class="sxs-lookup"><span data-stu-id="660e1-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="660e1-159">Wählen Sie die letzten fünf Felder (**Region**, **Postal Code**, **Country**, **Phone**und **Fax**) und ihre zugeordneten Bezeichnungen aus, und verschieben Sie sie nach oben rechts neben die ersten sechs Felder.</span><span class="sxs-lookup"><span data-stu-id="660e1-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="660e1-160">Wählen Sie die Elementvorlage (oberer Bereich des Steuerelements) aus.</span><span class="sxs-lookup"><span data-stu-id="660e1-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="660e1-161">Legen Sie im Eigenschaftenfenster die Eigenschaft **Größe** auf `427, 170`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="660e1-162">An diesem Punkt haben Sie eine funktionierende Anwendung, die eine sich wiederholende Liste von Kunden anzeigt.</span><span class="sxs-lookup"><span data-stu-id="660e1-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="660e1-163">Drücken Sie F5, um die Anwendung auszuführen, die Daten zu ändern und Kundendatensätze hinzuzufügen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="660e1-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="660e1-164">Im nächsten optionalen Schritt erfahren Sie, wie Sie zum Anpassen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="660e1-165">Nächste Schritte (optional)</span><span class="sxs-lookup"><span data-stu-id="660e1-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="660e1-166">Dieser Teil der exemplarischen Vorgehensweise besteht aus vier optionalen Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="660e1-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="660e1-167">Ändern der Darstellung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="660e1-168">Verhindern, dass Benutzer Datensätze hinzufügen oder löschen</span><span class="sxs-lookup"><span data-stu-id="660e1-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="660e1-169">Hinzufügen einer Suchfunktion zu den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="660e1-170">Hinzufügen einer Tabelle Master und Details zu den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="660e1-171">Ändern der Darstellung des DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="660e1-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="660e1-172">In diesem optionalen Schritt ändern Sie die `BackColor` von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelements zur Entwurfszeit.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="660e1-173">Sie fügen auch Code hinzu, um Zeilen in unterschiedlichen Farben anzuzeigen und die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="660e1-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="660e1-174">So ändern Sie die Darstellung des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="660e1-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="660e1-175">Wählen Sie in der Windows Forms-Designer den Hauptbereich (unten), der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="660e1-176">Legen Sie im Eigenschaftenfenster die Eigenschaft `BackColor` auf „White“ fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="660e1-177">Doppelklicken Sie auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>um den Code-Editor zu öffnen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="660e1-178">Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="660e1-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="660e1-179">In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>-Ereignishandler, fügen Sie den folgenden Code, um alternative der `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="660e1-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     <span data-ttu-id="660e1-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="660e1-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span></span>  
  
6.  <span data-ttu-id="660e1-181">In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>Ereignishandler, fügen Sie folgenden Code zum Ändern der `ForeColor` einer Bezeichnung abhängig von einer Bedingung:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="660e1-181">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     <span data-ttu-id="660e1-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="660e1-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span></span>  
  
7.  <span data-ttu-id="660e1-183">Drücken Sie F5, um die Anwendung auszuführen und die Anpassungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="660e1-183">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="660e1-184">Verhindern, dass Benutzer Datensätze hinzufügen oder löschen</span><span class="sxs-lookup"><span data-stu-id="660e1-184">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="660e1-185">In diesem optionalen Schritt fügen Sie Code, der verhindert, dass Benutzer hinzufügen oder Löschen von Datensätzen in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-185">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="660e1-186">So verhindern Sie, dass Benutzer Datensätze hinzufügt oder löscht</span><span class="sxs-lookup"><span data-stu-id="660e1-186">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="660e1-187">Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="660e1-187">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="660e1-188">Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="660e1-188">Add the following code to the `Form_Load` event:</span></span>  
  
     <span data-ttu-id="660e1-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="660e1-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span></span>  
  
3.  <span data-ttu-id="660e1-190">Klicken Sie in der Dropdownliste „Klassenname“ auf **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="660e1-190">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="660e1-191">Klicken Sie in der Dropdownliste „Methodenname“ auf **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="660e1-191">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="660e1-192">Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="660e1-192">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     <span data-ttu-id="660e1-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="660e1-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="660e1-194">Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource>ermöglicht die **DeleteItem** Schaltfläche jeder Änderung des aktuellen Datensatzes.</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="660e1-194">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="660e1-195">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="660e1-195">Press F5 to run the application.</span></span> <span data-ttu-id="660e1-196">Beachten Sie, dass die **DeleteItem** -Schaltfläche deaktiviert ist und dass Sie keine Elemente durch Drücken der ENTF-Taste löschen können.</span><span class="sxs-lookup"><span data-stu-id="660e1-196">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="660e1-197">Hinzufügen einer Suchfunktion zum DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="660e1-197">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="660e1-198">In diesem optionalen Schritt implementieren Sie die Funktion zum Suchen nach einem Wert in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-198">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="660e1-199">Wenn die Suchzeichenfolge gefunden wird, wählt das Steuerelement das Element aus, das den Wert enthält, und führt einen Bildlauf zum Element durch.</span><span class="sxs-lookup"><span data-stu-id="660e1-199">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="660e1-200">So fügen Sie eine Suchfunktion hinzu</span><span class="sxs-lookup"><span data-stu-id="660e1-200">To add search capability</span></span>  
  
1.  <span data-ttu-id="660e1-201">Ziehen Sie eine <xref:System.Windows.Forms.TextBox>-Steuerelement aus der **Toolbox** auf das Formular mit den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="660e1-201">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="660e1-202">Positionieren Sie es unter der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-202">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="660e1-203">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="660e1-203">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="660e1-204">Ziehen Sie eine <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** auf das Formular mit den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="660e1-204">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="660e1-205">Positionieren Sie es unter der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-205">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="660e1-206">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="660e1-206">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="660e1-207">Ändern Sie die **Text** -Eigenschaft in **Search**.</span><span class="sxs-lookup"><span data-stu-id="660e1-207">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="660e1-208">Doppelklicken Sie auf die <xref:System.Windows.Forms.Button>Steuerelement, um den Code-Editor zu öffnen, und fügen Sie den folgenden Code der `SearchButton_Click` -Ereignishandler.</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="660e1-208">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="660e1-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="660e1-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span></span>  
  
6.  <span data-ttu-id="660e1-210">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="660e1-210">Press F5 to run the application.</span></span> <span data-ttu-id="660e1-211">Geben Sie eine Kunden-ID in **SearchTextBox** ein, und klicken Sie auf die Schaltfläche **Search** .</span><span class="sxs-lookup"><span data-stu-id="660e1-211">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="660e1-212">Hinzufügen einer Master- und Detailtabelle zum DataRepeater</span><span class="sxs-lookup"><span data-stu-id="660e1-212">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="660e1-213">In diesem optionalen Schritt fügen Sie eine zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement, um verbundene Aufträge für jeden Kunden anzuzeigen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-213">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="660e1-214">So fügen Sie eine Master- und Detailtabelle hinzu</span><span class="sxs-lookup"><span data-stu-id="660e1-214">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="660e1-215">Ziehen Sie eine zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** auf das Formular.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-215">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="660e1-216">Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `465, 25`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-216">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="660e1-217">Legen Sie für die **Größe** -Eigenschaft den Wert `315, 600`fest.</span><span class="sxs-lookup"><span data-stu-id="660e1-217">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="660e1-218">Erweitern Sie im **Datenquellenfenster** den Tabellenknoten **Customers** , und wählen Sie den Detailknoten für die Tabelle **Orders** aus.</span><span class="sxs-lookup"><span data-stu-id="660e1-218">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="660e1-219">Ändern Sie den Ablagetyp für die **Orders** -Tabelle in „Details“, indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.</span><span class="sxs-lookup"><span data-stu-id="660e1-219">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="660e1-220">Ziehen Sie das **Aufträge** Knoten auf den Elementvorlagenbereich (der obere Bereich) des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-220">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="660e1-221">Eine **OrdersBindingSource** -Komponente und eine **OrdersTableAdapter** -Komponente werden der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="660e1-221">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="660e1-222">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="660e1-222">Press F5 to run the application.</span></span> <span data-ttu-id="660e1-223">Wenn Sie jeden Kunden auswählen, in der ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>steuern, die Aufträge für diesen Kunden werden angezeigt, in der zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="660e1-223">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="660e1-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="660e1-224">See Also</span></span>  
 <span data-ttu-id="660e1-225">[Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-225">[Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-226"> [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-226"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-227"> [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-227"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-228"> [Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-228"> [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-229"> [Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-229"> [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-230"> [Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-230"> [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-231"> [Gewusst wie: Erstellen einer Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-231"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="660e1-232"> [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-232"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-233"> [Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="660e1-233"> [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span></span>  
<span data-ttu-id="660e1-234"> [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="660e1-234"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
