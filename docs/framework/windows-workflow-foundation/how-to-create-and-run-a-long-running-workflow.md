---
title: Erstellen und Ausführen eines Workflows mit langer Laufzeit
description: In diesem Artikel wird gezeigt, wie Sie eine Windows Forms Host Anwendung erstellen, die das Starten und fortsetzen mehrerer Workflow Instanzen und Workflow Persistenz unterstützt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 701788ac5575ad671afd56db3af4bd247efac8b1
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188464"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="ac425-103">Erstellen und Ausführen eines Workflows mit langer Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ac425-103">How to create and run a long-running workflow</span></span>

<span data-ttu-id="ac425-104">Eines der zentralen Features von Windows Workflow Foundation (WF) ist die Möglichkeit der Laufzeit, Workflows im Leerlauf dauerhaft in einer Datenbank zu speichern und zu entladen.</span><span class="sxs-lookup"><span data-stu-id="ac425-104">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="ac425-105">Die Schritte in Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) haben die Grundlagen des Workflow-Hosting mithilfe einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac425-105">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="ac425-106">Anhand von Beispielen wurde gezeigt, wie Workflows und Workflowlebenszyklus-Handler gestartet und Lesezeichen wiederaufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ac425-106">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="ac425-107">Um die Workflowpersistenz effektiv zu veranschaulichen, ist ein komplexerer Workflowhost erforderlich, der das Starten und Fortsetzen mehrerer Workflowinstanzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac425-107">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="ac425-108">In diesem Schritt des Lernprogramms wird veranschaulicht, wie eine Windows-Formularhostanwendung erstellt wird, die das Starten und Fortsetzen mehrerer Workflowinstanzen und die Workflowpersistenz unterstützt sowie die Grundlage für erweiterte Funktionen wie Nachverfolgung und Versionsverwaltung bildet, die in den folgenden Schritten des Lernprogramms veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="ac425-108">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>

> [!NOTE]
> <span data-ttu-id="ac425-109">In diesem Schritt des Tutorials und in den nachfolgenden Schritten werden alle drei Workflow Typen aus "Gewusst [wie: Erstellen eines Workflows](how-to-create-a-workflow.md)" verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac425-109">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="to-create-the-persistence-database"></a><span data-ttu-id="ac425-110">So erstellen Sie die Persistenzdatenbank</span><span class="sxs-lookup"><span data-stu-id="ac425-110">To create the persistence database</span></span>

1. <span data-ttu-id="ac425-111">Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung zum lokalen Server her, z. b. **.\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="ac425-111">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="ac425-112">Klicken Sie mit der rechten Maustaste auf den Knoten **Datenbanken** auf dem lokalen Server, und wählen Sie **neue Datenbank** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-112">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="ac425-113">Benennen Sie die neue Datenbank **WF45GettingStartedTutorial**, akzeptieren Sie alle anderen Werte, und wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-113">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac425-114">Stellen Sie sicher, dass Sie die **Create Database** -Berechtigung auf dem lokalen Server haben, bevor Sie die Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac425-114">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>

2. <span data-ttu-id="ac425-115">Wählen Sie im Menü **Datei** die Option **Öffnen** und dann **Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-115">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="ac425-116">Navigieren Sie zum folgenden Ordner: *C:\WINDOWS\Microsoft.Net\Framework\v4.0.30319\sql\en*</span><span class="sxs-lookup"><span data-stu-id="ac425-116">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span></span>

    <span data-ttu-id="ac425-117">Wählen Sie die folgenden beiden Dateien aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="ac425-117">Select the following two files and click **Open**.</span></span>

    - <span data-ttu-id="ac425-118">*SqlWorkflowInstanceStoreLogic.sql*</span><span class="sxs-lookup"><span data-stu-id="ac425-118">*SqlWorkflowInstanceStoreLogic.sql*</span></span>

    - <span data-ttu-id="ac425-119">*SqlWorkflowInstanceStoreSchema.sql*</span><span class="sxs-lookup"><span data-stu-id="ac425-119">*SqlWorkflowInstanceStoreSchema.sql*</span></span>

3. <span data-ttu-id="ac425-120">Wählen Sie im Menü **Fenster** die Option **SqlWorkflowInstanceStoreSchema. SQL** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-120">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="ac425-121">Stellen Sie sicher, dass **WF45GettingStartedTutorial** in der Dropdown Liste **Verfügbare Datenbanken** ausgewählt ist, und klicken Sie im Menü **Abfrage** auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ac425-121">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

4. <span data-ttu-id="ac425-122">Wählen Sie im Menü **Fenster** die Option **SqlWorkflowInstanceStoreLogic. SQL** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-122">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="ac425-123">Stellen Sie sicher, dass **WF45GettingStartedTutorial** in der Dropdown Liste **Verfügbare Datenbanken** ausgewählt ist, und klicken Sie im Menü **Abfrage** auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ac425-123">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

    > [!WARNING]
    > <span data-ttu-id="ac425-124">Es ist wichtig, die vorherigen beiden Schritte in der richtigen Reihenfolge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac425-124">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="ac425-125">Wenn die Abfragen nicht in der richtigen Reihenfolge ausgeführt werden, treten Fehler auf, und die Persistenzdatenbank wird nicht richtig konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac425-125">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a><span data-ttu-id="ac425-126">So fügen Sie den DurableInstancing-Assemblys den Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="ac425-126">To add the reference to the DurableInstancing assemblies</span></span>

1. <span data-ttu-id="ac425-127">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflow** Message", und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ac425-127">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>

2. <span data-ttu-id="ac425-128">Wählen **Sie** Assemblys aus der Liste **Verweis hinzufügen** aus, und geben Sie im Feld Assemblys `DurableInstancing` **Suchen** ein</span><span class="sxs-lookup"><span data-stu-id="ac425-128">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="ac425-129">Dadurch werden die Assemblys gefiltert, sodass die gewünschten Verweise einfacher auszuwählen sind.</span><span class="sxs-lookup"><span data-stu-id="ac425-129">This filters the assemblies and makes the desired references easier to select.</span></span>

3. <span data-ttu-id="ac425-130">Aktivieren Sie das Kontrollkästchen neben **System. Activities. DurableInstancing** und **System. Runtime. DurableInstancing** in der Liste **Suchergebnisse** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac425-130">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>

## <a name="to-create-the-workflow-host-form"></a><span data-ttu-id="ac425-131">So erstellen Sie das Hostformular für den Workflow</span><span class="sxs-lookup"><span data-stu-id="ac425-131">To create the workflow host form</span></span>

1. <span data-ttu-id="ac425-132">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** " und wählen Sie **Hinzufügen**, **Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="ac425-132">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>

2. <span data-ttu-id="ac425-133">Wählen Sie in der Liste **installierte** Vorlagen die Option **Windows Form** aus, geben Sie `WorkflowHostForm` in das Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ac425-133">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>

3. <span data-ttu-id="ac425-134">Konfigurieren Sie die folgenden Eigenschaften für das Formular.</span><span class="sxs-lookup"><span data-stu-id="ac425-134">Configure the following properties on the form.</span></span>

    |<span data-ttu-id="ac425-135">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ac425-135">Property</span></span>|<span data-ttu-id="ac425-136">Wert</span><span class="sxs-lookup"><span data-stu-id="ac425-136">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="ac425-137">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="ac425-137">FormBorderStyle</span></span>|<span data-ttu-id="ac425-138">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="ac425-138">FixedSingle</span></span>|
    |<span data-ttu-id="ac425-139">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="ac425-139">MaximizeBox</span></span>|<span data-ttu-id="ac425-140">False</span><span class="sxs-lookup"><span data-stu-id="ac425-140">False</span></span>|
    |<span data-ttu-id="ac425-141">Size</span><span class="sxs-lookup"><span data-stu-id="ac425-141">Size</span></span>|<span data-ttu-id="ac425-142">400, 420</span><span class="sxs-lookup"><span data-stu-id="ac425-142">400, 420</span></span>|

4. <span data-ttu-id="ac425-143">Fügen Sie dem Formular die folgenden Steuerelemente in der angegebenen Reihenfolge hinzu, und konfigurieren Sie die Eigenschaften wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac425-143">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>

    |<span data-ttu-id="ac425-144">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ac425-144">Control</span></span>|<span data-ttu-id="ac425-145">Eigenschaft: Wert</span><span class="sxs-lookup"><span data-stu-id="ac425-145">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="ac425-146">**Schaltfläche**</span><span class="sxs-lookup"><span data-stu-id="ac425-146">**Button**</span></span>|<span data-ttu-id="ac425-147">Name: neues Spiel</span><span class="sxs-lookup"><span data-stu-id="ac425-147">Name: NewGame</span></span><br /><br /> <span data-ttu-id="ac425-148">Speicherort: 13, 13</span><span class="sxs-lookup"><span data-stu-id="ac425-148">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="ac425-149">Größe: 75, 23</span><span class="sxs-lookup"><span data-stu-id="ac425-149">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ac425-150">Text: neues Spiel</span><span class="sxs-lookup"><span data-stu-id="ac425-150">Text: New Game</span></span>|
    |<span data-ttu-id="ac425-151">**Bezeichnung**</span><span class="sxs-lookup"><span data-stu-id="ac425-151">**Label**</span></span>|<span data-ttu-id="ac425-152">Standort: 94, 18</span><span class="sxs-lookup"><span data-stu-id="ac425-152">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="ac425-153">Text: erraten einer Zahl zwischen 1 und</span><span class="sxs-lookup"><span data-stu-id="ac425-153">Text: Guess a number from 1 to</span></span>|
    |<span data-ttu-id="ac425-154">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-154">**ComboBox**</span></span>|<span data-ttu-id="ac425-155">Name: anzahlbereich</span><span class="sxs-lookup"><span data-stu-id="ac425-155">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="ac425-156">DropDownStyle: Dropdown List</span><span class="sxs-lookup"><span data-stu-id="ac425-156">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ac425-157">Elemente: 10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="ac425-157">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="ac425-158">Standort: 228, 12</span><span class="sxs-lookup"><span data-stu-id="ac425-158">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="ac425-159">Größe: 143, 21</span><span class="sxs-lookup"><span data-stu-id="ac425-159">Size: 143, 21</span></span>|
    |<span data-ttu-id="ac425-160">**Bezeichnung**</span><span class="sxs-lookup"><span data-stu-id="ac425-160">**Label**</span></span>|<span data-ttu-id="ac425-161">Speicherort: 13, 43</span><span class="sxs-lookup"><span data-stu-id="ac425-161">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="ac425-162">Text: Workflowtyp</span><span class="sxs-lookup"><span data-stu-id="ac425-162">Text: Workflow type</span></span>|
    |<span data-ttu-id="ac425-163">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-163">**ComboBox**</span></span>|<span data-ttu-id="ac425-164">Name: WorkflowType</span><span class="sxs-lookup"><span data-stu-id="ac425-164">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="ac425-165">DropDownStyle: Dropdown List</span><span class="sxs-lookup"><span data-stu-id="ac425-165">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ac425-166">Elemente: statemachinenumberguess Workflow, flowchartnumguess Workflow, sequentialnumguess Workflow</span><span class="sxs-lookup"><span data-stu-id="ac425-166">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="ac425-167">Speicherort: 94, 40</span><span class="sxs-lookup"><span data-stu-id="ac425-167">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="ac425-168">Größe: 277, 21</span><span class="sxs-lookup"><span data-stu-id="ac425-168">Size: 277, 21</span></span>|
    |<span data-ttu-id="ac425-169">**Bezeichnung**</span><span class="sxs-lookup"><span data-stu-id="ac425-169">**Label**</span></span>|<span data-ttu-id="ac425-170">Name: workflowversion</span><span class="sxs-lookup"><span data-stu-id="ac425-170">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="ac425-171">Speicherort: 13, 362</span><span class="sxs-lookup"><span data-stu-id="ac425-171">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="ac425-172">Text: Workflow Version</span><span class="sxs-lookup"><span data-stu-id="ac425-172">Text: Workflow version</span></span>|
    |<span data-ttu-id="ac425-173">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-173">**GroupBox**</span></span>|<span data-ttu-id="ac425-174">Speicherort: 13, 67</span><span class="sxs-lookup"><span data-stu-id="ac425-174">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="ac425-175">Größe: 358, 287</span><span class="sxs-lookup"><span data-stu-id="ac425-175">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="ac425-176">Text: Spiel</span><span class="sxs-lookup"><span data-stu-id="ac425-176">Text: Game</span></span>|

    > [!NOTE]
    > <span data-ttu-id="ac425-177">Wenn Sie die folgenden Steuerelemente hinzufügen, platzieren Sie Sie in der GroupBox.</span><span class="sxs-lookup"><span data-stu-id="ac425-177">When adding the following controls, put them into the GroupBox.</span></span>

    |<span data-ttu-id="ac425-178">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ac425-178">Control</span></span>|<span data-ttu-id="ac425-179">Eigenschaft: Wert</span><span class="sxs-lookup"><span data-stu-id="ac425-179">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="ac425-180">**Bezeichnung**</span><span class="sxs-lookup"><span data-stu-id="ac425-180">**Label**</span></span>|<span data-ttu-id="ac425-181">Speicherort: 7, 20</span><span class="sxs-lookup"><span data-stu-id="ac425-181">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="ac425-182">Text: Workflow Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="ac425-182">Text: Workflow Instance Id</span></span>|
    |<span data-ttu-id="ac425-183">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-183">**ComboBox**</span></span>|<span data-ttu-id="ac425-184">Name: InstanceId</span><span class="sxs-lookup"><span data-stu-id="ac425-184">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="ac425-185">DropDownStyle: Dropdown List</span><span class="sxs-lookup"><span data-stu-id="ac425-185">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ac425-186">Speicherort: 121, 17</span><span class="sxs-lookup"><span data-stu-id="ac425-186">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="ac425-187">Größe: 227, 21</span><span class="sxs-lookup"><span data-stu-id="ac425-187">Size: 227, 21</span></span>|
    |<span data-ttu-id="ac425-188">**Bezeichnung**</span><span class="sxs-lookup"><span data-stu-id="ac425-188">**Label**</span></span>|<span data-ttu-id="ac425-189">Speicherort: 7, 47</span><span class="sxs-lookup"><span data-stu-id="ac425-189">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="ac425-190">Text: erraten</span><span class="sxs-lookup"><span data-stu-id="ac425-190">Text: Guess</span></span>|
    |<span data-ttu-id="ac425-191">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-191">**TextBox**</span></span>|<span data-ttu-id="ac425-192">Name: erraten</span><span class="sxs-lookup"><span data-stu-id="ac425-192">Name: Guess</span></span><br /><br /> <span data-ttu-id="ac425-193">Speicherort: 50, 44</span><span class="sxs-lookup"><span data-stu-id="ac425-193">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="ac425-194">Größe: 65, 20</span><span class="sxs-lookup"><span data-stu-id="ac425-194">Size: 65, 20</span></span>|
    |<span data-ttu-id="ac425-195">**Schaltfläche**</span><span class="sxs-lookup"><span data-stu-id="ac425-195">**Button**</span></span>|<span data-ttu-id="ac425-196">Name: EnterGuess</span><span class="sxs-lookup"><span data-stu-id="ac425-196">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="ac425-197">Speicherort: 121, 42</span><span class="sxs-lookup"><span data-stu-id="ac425-197">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="ac425-198">Größe: 75, 23</span><span class="sxs-lookup"><span data-stu-id="ac425-198">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ac425-199">Text: Geben Sie Guess ein.</span><span class="sxs-lookup"><span data-stu-id="ac425-199">Text: Enter Guess</span></span>|
    |<span data-ttu-id="ac425-200">**Schaltfläche**</span><span class="sxs-lookup"><span data-stu-id="ac425-200">**Button**</span></span>|<span data-ttu-id="ac425-201">Name: quitgame</span><span class="sxs-lookup"><span data-stu-id="ac425-201">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="ac425-202">Speicherort: 274, 42</span><span class="sxs-lookup"><span data-stu-id="ac425-202">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="ac425-203">Größe: 75, 23</span><span class="sxs-lookup"><span data-stu-id="ac425-203">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ac425-204">Text: beenden</span><span class="sxs-lookup"><span data-stu-id="ac425-204">Text: Quit</span></span>|
    |<span data-ttu-id="ac425-205">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="ac425-205">**TextBox**</span></span>|<span data-ttu-id="ac425-206">Name: Workflow Status</span><span class="sxs-lookup"><span data-stu-id="ac425-206">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="ac425-207">Speicherort: 10, 73</span><span class="sxs-lookup"><span data-stu-id="ac425-207">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="ac425-208">Mehrzeilige Zeilen: true</span><span class="sxs-lookup"><span data-stu-id="ac425-208">Multiline: True</span></span><br /><br /> <span data-ttu-id="ac425-209">Schreibgeschützt: true</span><span class="sxs-lookup"><span data-stu-id="ac425-209">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="ac425-210">Scrollleisten: vertikal</span><span class="sxs-lookup"><span data-stu-id="ac425-210">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="ac425-211">Größe: 338, 208</span><span class="sxs-lookup"><span data-stu-id="ac425-211">Size: 338, 208</span></span>|

5. <span data-ttu-id="ac425-212">Legen Sie die Eigenschaft " **akzeptbutton** " des Formulars auf " **EnterGuess**" fest.</span><span class="sxs-lookup"><span data-stu-id="ac425-212">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>

 <span data-ttu-id="ac425-213">Im folgenden Beispiel wird das abgeschlossene Formular dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-213">The following example illustrates the completed form.</span></span>

 ![Screenshot eines Windows Workflow Foundation Workflow-Host Formulars.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a><span data-ttu-id="ac425-215">So fügen Sie die Eigenschaften und Hilfsmethoden des Formulars hinzu</span><span class="sxs-lookup"><span data-stu-id="ac425-215">To add the properties and helper methods of the form</span></span>

<span data-ttu-id="ac425-216">Durch die Schritte in diesem Abschnitt werden der Formularklasse Eigenschaften und Hilfsmethoden hinzugefügt, die die Benutzeroberfläche des Formulars so konfigurieren, dass sie das Ausführen und Fortsetzen der Workflows zum Schätzen von Zahlen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ac425-216">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>

1. <span data-ttu-id="ac425-217">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **workflowhostform** , und wählen Sie **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-217">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>

2. <span data-ttu-id="ac425-218">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-218">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="ac425-219">Fügen Sie der **workflowhostform** -Klasse die folgenden Member-Deklarationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-219">Add the following member declarations to the **WorkflowHostForm** class.</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > <span data-ttu-id="ac425-220">Wenn Ihre Verbindungszeichenfolge abweicht, aktualisieren Sie `connectionString`, damit sie auf Ihre Datenbank verweist.</span><span class="sxs-lookup"><span data-stu-id="ac425-220">If your connection string is different, update `connectionString` to refer to your database.</span></span>

4. <span data-ttu-id="ac425-221">Fügen Sie der `WorkflowInstanceId`-Klasse eine `WorkflowFormHost`-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-221">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    <span data-ttu-id="ac425-222">Das Kombinations `InstanceId` Feld zeigt eine Liste der beibehaltenen Workflow Instanz-IDs an, und die- `WorkflowInstanceId` Eigenschaft gibt den aktuell ausgewählten Workflow zurück.</span><span class="sxs-lookup"><span data-stu-id="ac425-222">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>

5. <span data-ttu-id="ac425-223">Fügen Sie einen Handler für das `Load`-Ereignis des Formulars hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-223">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="ac425-224">Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse** , und doppelklicken Sie dann auf **Laden**.</span><span class="sxs-lookup"><span data-stu-id="ac425-224">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. <span data-ttu-id="ac425-225">Fügen Sie `WorkflowHostForm_Load` den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-225">Add the following code to `WorkflowHostForm_Load`.</span></span>

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    <span data-ttu-id="ac425-226">Beim Laden des Formulars geschieht Folgendes: `SqlWorkflowInstanceStore` wird konfiguriert, der Bereich und die Kombinationsfelder für den Workflowtyp werden auf die Standardwerte festgelegt, und die persistenten Workflowinstanzen werden dem Kombinationsfeld `InstanceId` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac425-226">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>

7. <span data-ttu-id="ac425-227">Fügen Sie einen `SelectedIndexChanged`-Handler für `InstanceId` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-227">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="ac425-228">Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, wählen Sie das Kombinations `InstanceId` Feld aus, klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse** , und doppelklicken Sie auf **SelectedIndexChanged**.</span><span class="sxs-lookup"><span data-stu-id="ac425-228">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. <span data-ttu-id="ac425-229">Fügen Sie `InstanceId_SelectedIndexChanged` den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-229">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="ac425-230">Sobald der Benutzer über das Kombinationsfeld einen Workflow auswählt, wird das Statusfenster von diesem Handler aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ac425-230">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. <span data-ttu-id="ac425-231">Fügen Sie der Formularklasse die folgende `ListPersistedWorkflows`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-231">Add the following `ListPersistedWorkflows` method to the form class.</span></span>

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    <span data-ttu-id="ac425-232">`ListPersistedWorkflows` fragt den Instanzspeicher für persistente Workflowinstanzen ab und fügt dem Kombinationsfeld `cboInstanceId` die Instanz-IDs hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-232">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>

10. <span data-ttu-id="ac425-233">Fügen Sie der Formularklasse die folgende `UpdateStatus`-Methode und den entsprechenden Delegaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-233">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="ac425-234">Durch diese Methode wird das Statusfenster auf dem Formular mit dem Status des derzeit ausgeführten Workflows aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ac425-234">This method updates the status window on the form with the status of the currently running workflow.</span></span>

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. <span data-ttu-id="ac425-235">Fügen Sie der Formularklasse die folgende `GameOver`-Methode und den entsprechenden Delegaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-235">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="ac425-236">Wenn ein Workflow abgeschlossen ist, aktualisiert diese Methode die Benutzeroberfläche des Formulars, indem die Instanz-ID des abgeschlossenen Workflows aus dem Kombinations Feld **InstanceId** entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-236">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><span data-ttu-id="ac425-237">So konfigurieren Sie den Instanzspeicher, die Handler für den Workflowlebenszyklus und Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="ac425-237">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>

1. <span data-ttu-id="ac425-238">Fügen Sie der Formularklasse eine `ConfigureWorkflowApplication`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-238">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    <span data-ttu-id="ac425-239">Durch diese Methode wird `WorkflowApplication` konfiguriert und die gewünschten Erweiterungen sowie Handler für die Lebenszyklusereignisse des Workflows werden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac425-239">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>

2. <span data-ttu-id="ac425-240">Geben Sie in `ConfigureWorkflowApplication` den `SqlWorkflowInstanceStore` für `WorkflowApplication` an.</span><span class="sxs-lookup"><span data-stu-id="ac425-240">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. <span data-ttu-id="ac425-241">Als Nächstes erstellen Sie eine `StringWriter`-Instanz und fügen sie der `Extensions`-Auflistung von `WorkflowApplication` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-241">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="ac425-242">Wenn eine `StringWriter` zu den Erweiterungen hinzugefügt wird, erfasst Sie alle `WriteLine` Aktivitäts Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="ac425-242">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="ac425-243">Sobald der Workflow im Leerlauf ist, kann die `WriteLine` Ausgabe aus `StringWriter` extrahiert und im Formular angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac425-243">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. <span data-ttu-id="ac425-244">Fügen Sie folgenden Handler für das `Completed`-Ereignis hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-244">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="ac425-245">Sobald ein Workflow erfolgreich abgeschlossen ist, wird die Anzahl der Durchläufe zum Schätzen der Zahl im Statusfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac425-245">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="ac425-246">Bei Beendigung des Workflows werden die Ausnahmeinformationen, die zur Beendigung geführt haben, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac425-246">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="ac425-247">Am Ende des Handlers wird die `GameOver`-Methode aufgerufen, durch die der abgeschlossene Workflow aus der Workflowliste entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-247">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. <span data-ttu-id="ac425-248">Fügen Sie den folgenden `Aborted`-Handler und `OnUnhandledException`-Handler hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-248">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="ac425-249">Die `GameOver`-Methode wird nicht vom `Aborted`-Handler aufgerufen, da eine Workflowinstanz beim Abbruch nicht beendet wird. Es besteht keine Möglichkeit, die Instanz zu einem späteren Zeitpunkt fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ac425-249">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. <span data-ttu-id="ac425-250">Fügen Sie den folgenden `PersistableIdle`-Handler hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-250">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="ac425-251">Dieser Handler ruft die hinzugefügte `StringWriter` Erweiterung ab, extrahiert die Ausgabe aus den `WriteLine`-Aktivitäten und zeigt sie im Statusfenster an.</span><span class="sxs-lookup"><span data-stu-id="ac425-251">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    <span data-ttu-id="ac425-252">Die <xref:System.Activities.PersistableIdleAction>-Enumeration besitzt drei Werte: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist> und <xref:System.Activities.PersistableIdleAction.Unload>.</span><span class="sxs-lookup"><span data-stu-id="ac425-252">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="ac425-253"><xref:System.Activities.PersistableIdleAction.Persist> bewirkt, dass der Workflow persistent gespeichert wird, jedoch nicht, dass der Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-253"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="ac425-254"><xref:System.Activities.PersistableIdleAction.Unload> bewirkt, dass der Workflow persistent gespeichert und entladen wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-254"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>

    <span data-ttu-id="ac425-255">Im folgenden Beispiel ist die abgeschlossene `ConfigureWorkflowApplication`-Methode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-255">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a><span data-ttu-id="ac425-256">So aktivieren Sie das Starten und Fortsetzen mehrerer Workflowtypen</span><span class="sxs-lookup"><span data-stu-id="ac425-256">To enable starting and resuming multiple workflow types</span></span>

<span data-ttu-id="ac425-257">Um eine Workflowinstanz fortzusetzen, muss der Host die Workflowdefinition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ac425-257">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="ac425-258">In diesem Lernprogramm werden drei Workflowtypen verwendet, von denen in den folgenden Schritten mehrere Versionen vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac425-258">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="ac425-259">`WorkflowIdentity` ermöglicht einer Hostanwendung, einer persistenten Workflowinstanz Identifikationsinformationen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ac425-259">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="ac425-260">Die Schritte in diesem Abschnitt veranschaulichen das Erstellen einer Hilfsprogrammklasse, die das Zuordnen der Workflowidentität von einer persistenten Workflowinstanz zur entsprechenden Workflowdefinition unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac425-260">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="ac425-261">Weitere Informationen zu `WorkflowIdentity` und zur Versionsverwaltung finden [Sie unter Verwenden von workflowidentity und Versions](using-workflowidentity-and-versioning.md)Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="ac425-261">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

1. <span data-ttu-id="ac425-262">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** **", und** wählen Sie **Hinzufügen**,</span><span class="sxs-lookup"><span data-stu-id="ac425-262">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="ac425-263">Geben `WorkflowVersionMap` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ac425-263">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>

2. <span data-ttu-id="ac425-264">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-264">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. <span data-ttu-id="ac425-265">Ersetzen Sie die Deklaration der `WorkflowVersionMap`-Klasse durch die folgende Deklaration.</span><span class="sxs-lookup"><span data-stu-id="ac425-265">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
       }
    }
    ```

    <span data-ttu-id="ac425-266">`WorkflowVersionMap` enthält drei Workflowidentitäten, die den drei Workflowdefinitionen aus diesem Lernprogramm zugeordnet werden, und wird in den folgenden Abschnitten beim Starten und Fortsetzen von Workflows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac425-266">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>

## <a name="to-start-a-new-workflow"></a><span data-ttu-id="ac425-267">So starten Sie einen neuen Workflow</span><span class="sxs-lookup"><span data-stu-id="ac425-267">To start a new workflow</span></span>

1. <span data-ttu-id="ac425-268">Fügen Sie einen `Click`-Handler für `NewGame` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-268">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="ac425-269">Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `NewGame` .</span><span class="sxs-lookup"><span data-stu-id="ac425-269">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="ac425-270">Ein `NewGame_Click`-Handler wird hinzugefügt, und die Ansicht wechselt zur Codeansicht für das Formular.</span><span class="sxs-lookup"><span data-stu-id="ac425-270">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="ac425-271">Sobald der Benutzer auf diese Schaltfläche klickt, wird ein neuer Workflow gestartet.</span><span class="sxs-lookup"><span data-stu-id="ac425-271">Whenever the user clicks this button a new workflow is started.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="ac425-272">Fügen Sie dem Click-Handler folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-272">Add the following code to the click handler.</span></span> <span data-ttu-id="ac425-273">Durch diesen Code wird ein Wörterbuch mit Eingabeargumenten für den Workflow erstellt, die nach Argumentnamen geordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ac425-273">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="ac425-274">Das Wörterbuch verfügt über einen Eintrag, der den Bereich der zufällig generierten Zahl enthält, die vom Bereichskombinationsfeld abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-274">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. <span data-ttu-id="ac425-275">Als Nächstes fügen Sie den folgenden Code hinzu, durch den der Workflow gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-275">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="ac425-276">`WorkflowIdentity` und die Workflowdefinition, die dem Typ des ausgewählten Workflows entspricht, werden mithilfe der `WorkflowVersionMap`-Hilfsklasse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac425-276">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="ac425-277">Anschließend wird eine neue `WorkflowApplication`-Instanz mithilfe von Workflowdefinition, `WorkflowIdentity` und des Wörterbuchs mit Eingabeargumenten erstellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-277">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. <span data-ttu-id="ac425-278">Als Nächstes fügen Sie den folgenden Code hinzu, durch den der Workflowliste der Workflow hinzugefügt und die Versionsinformationen des Workflows für das Formular angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac425-278">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. <span data-ttu-id="ac425-279">Rufen Sie `ConfigureWorkflowApplication` auf, um den Instanzspeicher, die Erweiterungen und die Workflowlebenszyklus-Handler für diese `WorkflowApplication`-Instanz zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ac425-279">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. <span data-ttu-id="ac425-280">Rufen Sie abschließend `Run` auf.</span><span class="sxs-lookup"><span data-stu-id="ac425-280">Finally, call `Run`.</span></span>

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     <span data-ttu-id="ac425-281">Im folgenden Beispiel ist der abgeschlossene `NewGame_Click`-Handler dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-281">The following example is the completed `NewGame_Click` handler.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a><span data-ttu-id="ac425-282">So setzen Sie einen Workflow fort</span><span class="sxs-lookup"><span data-stu-id="ac425-282">To resume a workflow</span></span>

1. <span data-ttu-id="ac425-283">Fügen Sie einen `Click`-Handler für `EnterGuess` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-283">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="ac425-284">Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `EnterGuess` .</span><span class="sxs-lookup"><span data-stu-id="ac425-284">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="ac425-285">Sobald der Benutzer auf diese Schaltfläche klickt, wird ein Workflow fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ac425-285">Whenever the user clicks this button a workflow is resumed.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="ac425-286">Fügen Sie den folgenden Code hinzu, um sicherzustellen, dass ein Workflow in der Workflowliste ausgewählt ist und dass der Schätzwert des Benutzers gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ac425-286">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. <span data-ttu-id="ac425-287">Rufen Sie anschließend die `WorkflowApplicationInstance` der resistenten Workflowinstanz ab.</span><span class="sxs-lookup"><span data-stu-id="ac425-287">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="ac425-288">`WorkflowApplicationInstance` stellt eine persistente Workflowinstanz dar, die noch keiner Workflowdefinition zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ac425-288">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="ac425-289">Die `DefinitionIdentity` von `WorkflowApplicationInstance` enthält die `WorkflowIdentity` der persistenten Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="ac425-289">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="ac425-290">In diesem Lernprogramm wird die `WorkflowVersionMap` Hilfsklasse verwendet, um `WorkflowIdentity` der richtigen Workflowdefinition zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ac425-290">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="ac425-291">Beim Abrufen der Workflowdefinition wird anhand der richtigen Workflowdefinition eine `WorkflowApplication` erstellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-291">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. <span data-ttu-id="ac425-292">Sobald `WorkflowApplication` erstellt wird, konfigurieren Sie den Instanzspeicher, die Handler des Workflowlebenszyklus und die Erweiterungen, indem Sie `ConfigureWorkflowApplication` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ac425-292">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="ac425-293">Diese Schritte müssen bei jeder Erstellung einer neuen `WorkflowApplication` ausgeführt werden, und zwar bevor die Workflowinstanz in `WorkflowApplication` geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-293">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="ac425-294">Nachdem der Workflow geladen wurde, wird er mit der Schätzung des Benutzers fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ac425-294">After the workflow is loaded, it is resumed with the user's guess.</span></span>

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. <span data-ttu-id="ac425-295">Löschen Sie abschließend den Eintrag im Textfeld, und bereiten Sie das Formular für die Eingabe eines anderen Schätzwerts vor.</span><span class="sxs-lookup"><span data-stu-id="ac425-295">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    <span data-ttu-id="ac425-296">Im folgenden Beispiel ist der abgeschlossene `EnterGuess_Click`-Handler dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ac425-296">The following example is the completed `EnterGuess_Click` handler.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a><span data-ttu-id="ac425-297">So beenden Sie einen Workflow</span><span class="sxs-lookup"><span data-stu-id="ac425-297">To terminate a workflow</span></span>

1. <span data-ttu-id="ac425-298">Fügen Sie einen `Click`-Handler für `QuitGame` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-298">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="ac425-299">Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `QuitGame` .</span><span class="sxs-lookup"><span data-stu-id="ac425-299">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="ac425-300">Sobald der Benutzer auf diese Schaltfläche klickt, wird der aktuell ausgewählte Workflow beendet.</span><span class="sxs-lookup"><span data-stu-id="ac425-300">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="ac425-301">Fügen Sie dem `QuitGame_Click`-Handler folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-301">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="ac425-302">Durch diesen Code wird zuerst überprüft, ob in der Workflowliste ein Workflow ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ac425-302">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="ac425-303">Anschließend lädt er die persistente Instanz in eine `WorkflowApplicationInstance`, ermittelt anhand von `DefinitionIdentity` die richtige Workflowdefinition und initialisiert die `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="ac425-303">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="ac425-304">Als Nächstes werden die Erweiterungen und die Workflowlebenszyklus-Handler mit einem Aufruf von `ConfigureWorkflowApplication` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac425-304">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="ac425-305">Sobald `WorkflowApplication` konfiguriert ist, wird sie geladen, und `Terminate` wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac425-305">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a><span data-ttu-id="ac425-306">So erstellen Sie die Anwendung und führen sie aus</span><span class="sxs-lookup"><span data-stu-id="ac425-306">To build and run the application</span></span>

1. <span data-ttu-id="ac425-307">Doppelklicken Sie in **Projektmappen-Explorer** auf **Program.cs** (oder **Module1. vb**), um den Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac425-307">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>

2. <span data-ttu-id="ac425-308">Fügen Sie die folgende `using`-Anweisung (oder `Imports`-Anweisung) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac425-308">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="ac425-309">Entfernen Sie den vorhandenen Workflow-Hostingcode, oder kommentieren Sie ihn aus Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)aus, und ersetzen Sie ihn durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="ac425-309">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. <span data-ttu-id="ac425-310">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflow** Message", und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="ac425-310">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="ac425-311">Geben Sie auf der Registerkarte **Anwendung** die **Windows-Anwendung** für den **Ausgabetyp** an.</span><span class="sxs-lookup"><span data-stu-id="ac425-311">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="ac425-312">Dieser Schritt ist optional, wird er jedoch nicht ausgeführt, wird zusätzlich zum Formular das Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac425-312">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>

5. <span data-ttu-id="ac425-313">Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac425-313">Press Ctrl+Shift+B to build the application.</span></span>

6. <span data-ttu-id="ac425-314">Stellen Sie sicher, dass " **numguess Workflowhost** " als Start Anwendung festgelegt ist, und drücken Sie STRG + F5, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ac425-314">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>

7. <span data-ttu-id="ac425-315">Wählen Sie einen Bereich für das Ratespiel und den Typ des zu startenden Workflows aus, und klicken Sie auf **Neues Spiel**.</span><span class="sxs-lookup"><span data-stu-id="ac425-315">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="ac425-316">Geben Sie im Feld für die **Vermutung** einen Schätz Text ein, und klicken Sie auf " **Gehe** zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="ac425-316">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="ac425-317">Beachten Sie, dass die Ausgabe der `WriteLine`-Aktivitäten auf dem Formular angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ac425-317">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>

8. <span data-ttu-id="ac425-318">Starten Sie mehrere Workflows mit verschiedenen Workflow Typen und Zahlenbereichen, geben Sie einige Schätzwerte ein, und wechseln Sie zwischen den Workflows, indem Sie Sie aus der Liste der **workflowinstanzkennung**</span><span class="sxs-lookup"><span data-stu-id="ac425-318">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>

    <span data-ttu-id="ac425-319">Wenn Sie zu einem neuen Workflow wechseln, werden die vorherigen Schätzwerte und der Workflowverlauf nicht im Statusfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac425-319">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="ac425-320">Der Status ist nicht verfügbar, weil er nicht erfasst wurde und nirgends gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ac425-320">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="ac425-321">Im nächsten Schritt des Tutorials, Gewusst [wie: Erstellen eines benutzerdefinierten Überwachungs Teilnehmers](how-to-create-a-custom-tracking-participant.md), erstellen Sie einen benutzerdefinierten nach Verfolgungs Teilnehmer, der diese Informationen speichert.</span><span class="sxs-lookup"><span data-stu-id="ac425-321">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
