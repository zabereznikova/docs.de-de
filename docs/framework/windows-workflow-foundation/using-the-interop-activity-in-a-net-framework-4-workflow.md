---
title: Verwenden der Interop-Aktivität in einem .NET Framework 4-Workflow
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ebef74097d22c9624a29470f4cda231bbb32fe90
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="5525b-102">Verwenden der Interop-Aktivität in einem .NET Framework 4-Workflow</span><span class="sxs-lookup"><span data-stu-id="5525b-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="5525b-103">Mit [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] oder [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erstellte Aktivitäten können in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflow mithilfe der <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5525b-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="5525b-104">Dieses Thema enthält eine Übersicht über die Verwendung der <xref:System.Activities.Statements.Interop>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5525b-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5525b-105">Die <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designer angezeigt, es sei denn, das Projekt des Workflows dessen **Zielframework** eingestellt **.Net Framework 4** oder höher.</span><span class="sxs-lookup"><span data-stu-id="5525b-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="5525b-106">Verwenden der Interop-Aktivität in Workflows von .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="5525b-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="5525b-107">In diesem Thema wird eine [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivitätsbibliothek erstellt, die eine `DiscountCalculator`-Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="5525b-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="5525b-108">Der `DiscountCalculator` berechnet einen Rabatt auf Grundlage einer Kaufmenge. Er besteht aus einem <xref:System.Workflow.Activities.SequenceActivity>-Objekt, das ein <xref:System.Workflow.Activities.PolicyActivity>-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5525b-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5525b-109">Die in diesem Thema erstellte [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivität implementiert die Logik der Aktivität mithilfe eines <xref:System.Workflow.Activities.PolicyActivity>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="5525b-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="5525b-110">Die Verwendung von Regeln in einem [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Workflow erfordert weder eine benutzerdefinierte <xref:System.Activities.Statements.Interop>-Aktivität noch die [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5525b-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="5525b-111">Ein Beispiel der Verwendung von Regeln in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow ohne Verwendung der <xref:System.Activities.Statements.Interop> Aktivität, finden Sie unter der [Richtlinienaktivität in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5525b-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="5525b-112">So erstellen Sie das Projekt für die .NET Framework 3.5-Aktivitätsbibliothek</span><span class="sxs-lookup"><span data-stu-id="5525b-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="5525b-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , und wählen Sie **neu** und dann **Projekt...**</span><span class="sxs-lookup"><span data-stu-id="5525b-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="5525b-114">aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="5525b-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="5525b-115">Erweitern Sie die **andere Projekttypen** Knoten in der **installierte Vorlagen** und wählen **Visual Studio-Projektmappen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="5525b-116">Wählen Sie **leere Projektmappe** aus der **Visual Studio-Projektmappen** Liste.</span><span class="sxs-lookup"><span data-stu-id="5525b-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="5525b-117">Typ `PolicyInteropDemo` in der **Namen** Feld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="5525b-118">Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="5525b-119">Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="5525b-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="5525b-120">In der **installierte Vorlagen** Liste **Visual C#-** und dann **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="5525b-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="5525b-121">Wählen Sie **.NET Framework 3.5** aus .NET Framework Version Dropdown-Liste, und wählen Sie dann **Workflowaktivitätsbibliothek** aus der **Vorlagen** Liste.</span><span class="sxs-lookup"><span data-stu-id="5525b-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="5525b-122">Typ `PolicyActivityLibrary` in der **Namen** Feld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="5525b-123">Mit der rechten Maustaste **Activity1.cs** in **Projektmappen-Explorer** , und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="5525b-124">Klicken Sie zur Bestätigung auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="5525b-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="5525b-125">So erstellen Sie die DiscountCalculator-Aktivität</span><span class="sxs-lookup"><span data-stu-id="5525b-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="5525b-126">Mit der rechten Maustaste **PolicyActivityLibrary** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **Aktivität...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="5525b-127">Wählen Sie **Aktivität (mit getrenntem Code)** aus der **Visual C#-Elemente** Liste.</span><span class="sxs-lookup"><span data-stu-id="5525b-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="5525b-128">Typ `DiscountCalculator` in der **Namen** Feld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="5525b-129">Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="5525b-130">Fügen Sie der `DiscountCalculator`-Klasse die folgenden drei Eigenschaften hinzu:</span><span class="sxs-lookup"><span data-stu-id="5525b-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="5525b-131">Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** , und wählen Sie **Sicht-Designer**.</span><span class="sxs-lookup"><span data-stu-id="5525b-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="5525b-132">Ziehen Sie eine **Richtlinie** Aktivität aus der **Windows Workflow v3. 0** Teil der **Toolbox** und legen Sie sie in der **DiscountCalculator** Aktivität .</span><span class="sxs-lookup"><span data-stu-id="5525b-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="5525b-133">Wenn die **Toolbox** Fenster ist nicht sichtbar ist, wählen **Toolbox** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="5525b-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="5525b-134">So konfigurieren Sie die Regeln</span><span class="sxs-lookup"><span data-stu-id="5525b-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="5525b-135">Klicken Sie auf die neu hinzugefügte **Richtlinie** Aktivität, um diese auszuwählen, falls er nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5525b-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="5525b-136">Klicken Sie auf die **RuleSetReference** Eigenschaft in der **Eigenschaften** Fenster aus, um auszuwählen, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um die rechts neben der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5525b-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="5525b-137">Wenn die **Eigenschaften** nicht sichtbar ist, wählen Sie **Fenster "Eigenschaften"** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="5525b-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="5525b-138">Wählen Sie **klicken Sie auf neu...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="5525b-139">Klicken Sie auf **Regel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="5525b-140">Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="5525b-141">Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="5525b-142">Klicken Sie auf **Regel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="5525b-143">Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="5525b-144">Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="5525b-145">Klicken Sie auf **Regel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="5525b-146">Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="5525b-147">Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="5525b-148">Geben Sie den folgenden Ausdruck in der **Else-Aktionen** Feld.</span><span class="sxs-lookup"><span data-stu-id="5525b-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="5525b-149">Klicken Sie auf **OK** schließen die **Regelsatz-Editor** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="5525b-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="5525b-150">Sicherstellen, dass die neu erstellte <xref:System.Workflow.Activities.Rules.RuleSet> ausgewählt ist, der **Namen** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="5525b-151">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5525b-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="5525b-152">Die Regeln, die der `DiscountCalculator`-Aktivität in diesem Verfahren hinzugefügt wurden, sind im folgenden Codebeispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5525b-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="5525b-153">Wenn das <xref:System.Workflow.Activities.PolicyActivity>-Objekt ausgeführt wird, werten diese drei Regeln die Eigenschaftswerte `Subtotal`, `DiscountPercent` und `Total` der `DiscountCalculator`-Aktivität aus und ändern sie, um den gewünschten Rabatt zu errechnen.</span><span class="sxs-lookup"><span data-stu-id="5525b-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="5525b-154">Verwenden der DiscountCalculator-Aktivität mit der Interop-Aktivität</span><span class="sxs-lookup"><span data-stu-id="5525b-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="5525b-155">Damit die `DiscountCalculator`-Aktivität in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflow verwendet werden kann, kommt die <xref:System.Activities.Statements.Interop>-Aktivität zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="5525b-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="5525b-156">In diesem Abschnitt werden zwei Workflows erstellt – einer mithilfe von Code und einer mithilfe des Workflow-Designers –, um zu veranschaulichen, wie die <xref:System.Activities.Statements.Interop>-Aktivität mit der `DiscountCalculator`-Aktivität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5525b-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="5525b-157">Für beide Workflows wird die gleiche Hostanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5525b-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="5525b-158">So erstellen Sie die Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="5525b-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="5525b-159">Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, und klicken Sie dann **neues Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="5525b-160">Sicherstellen, dass **.NET Framework 4.5** , die in der Dropdownliste mit den .NET Framework-Version ausgewählt ist, und wählen Sie **Workflowkonsolenanwendung** aus der **Visual C#-Elemente** Liste.</span><span class="sxs-lookup"><span data-stu-id="5525b-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="5525b-161">Typ `PolicyInteropHost` in der **Namen** Feld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="5525b-162">Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5525b-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="5525b-163">In der **Zielframework** Dropdown-Liste, ändern Sie die Auswahl von **.NET Framework 4 Client Profile** auf **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="5525b-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="5525b-164">Klicken Sie auf **Ja** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5525b-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="5525b-165">Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="5525b-166">Wählen Sie **PolicyActivityLibrary** aus der **Projekte** Registerkarte, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="5525b-167">Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="5525b-168">Wählen Sie **System.Workflow.Activities**, **System.Workflow.ComponentModel**, und klicken Sie dann **System.Workflow.ComponentModel** aus der **.NET**Registerkarte, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="5525b-169">Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="5525b-170">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5525b-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="5525b-171">Verwenden der Interop-Aktivität im Code</span><span class="sxs-lookup"><span data-stu-id="5525b-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="5525b-172">In diesem Beispiel wird eine Workflowdefinition mithilfe von Code erstellt, der die <xref:System.Activities.Statements.Interop>-Aktivität und die `DiscountCalculator`-Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="5525b-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="5525b-173">Dieser Workflow wird mit dem <xref:System.Activities.WorkflowInvoker>-Objekt aufgerufen, und die Ergebnisse der Regelauswertung werden mithilfe der <xref:System.Activities.Statements.WriteLine>-Aktivität in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5525b-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="5525b-174">So verwenden Sie die Interop-Aktivität im Code</span><span class="sxs-lookup"><span data-stu-id="5525b-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="5525b-175">Mit der rechten Maustaste **"Program.cs"** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="5525b-176">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5525b-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="5525b-177">Entfernen Sie den Inhalt der `Main`-Methode, und ersetzen Sie ihn durch folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5525b-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="5525b-178">Erstellen Sie in der `Program`-Klasse eine neue Methode namens `CalculateDiscountUsingCodeWorkflow`, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="5525b-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5525b-179">Die Eigenschaften `Subtotal`, `DiscountPercent` und `Total` der `DiscountCalculator`-Aktivität werden als Argumente der <xref:System.Activities.Statements.Interop>-Aktivität verfügbar gemacht und an lokale Workflowvariablen in der <xref:System.Activities.Statements.Interop>-Auflistung der <xref:System.Activities.Statements.Interop.ActivityProperties%2A>-Aktivität gebunden.</span><span class="sxs-lookup"><span data-stu-id="5525b-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="5525b-180">`Subtotal` wird als <xref:System.Activities.ArgumentDirection.In>-Argument hinzugefügt, da die `Subtotal`-Daten in die <xref:System.Activities.Statements.Interop>-Aktivität übertragen werden, und `DiscountPercent` und `Total` werden als <xref:System.Activities.ArgumentDirection.Out>-Argumente hinzugefügt, da ihre Daten aus der <xref:System.Activities.Statements.Interop>-Aktivität übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="5525b-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="5525b-181">Beachten Sie, dass die zwei <xref:System.Activities.ArgumentDirection.Out>-Argumente unter den Namen `DiscountPercentOut` und `TotalOut` hinzugefügt werden, um zu kennzeichnen, dass sie <xref:System.Activities.ArgumentDirection.Out>-Argumente darstellen.</span><span class="sxs-lookup"><span data-stu-id="5525b-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="5525b-182">Der `DiscountCalculator`-Typ wird als <xref:System.Activities.Statements.Interop> der <xref:System.Activities.Statements.Interop.ActivityType%2A>-Aktivität angegeben.</span><span class="sxs-lookup"><span data-stu-id="5525b-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="5525b-183">Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5525b-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="5525b-184">Probieren Sie unterschiedliche Werte für den `Subtotal`-Wert aus, um die verschiedenen Rabattstufen zu testen, die von der `DiscountCalculator`-Aktivität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5525b-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="5525b-185">Verwenden der Interop-Aktivität im Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="5525b-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="5525b-186">In diesem Beispiel wird ein Workflow mithilfe des Workflow-Designers erstellt.</span><span class="sxs-lookup"><span data-stu-id="5525b-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="5525b-187">Dieser Workflow verfügt über die gleiche Funktionalität wie der Workflow im vorherigen Beispiel, hier wird der Rabatt jedoch nicht über eine <xref:System.Activities.Statements.WriteLine>-Aktivität angezeigt. Stattdessen ruft die Hostanwendung die Rabattinformationen ab, wenn der Workflow abgeschlossen wird, und zeigt sie dann an.</span><span class="sxs-lookup"><span data-stu-id="5525b-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="5525b-188">Außerdem sind die Daten nicht in lokalen Workflowvariablen enthalten. Die Argumente werden im Workflow-Designer erstellt, und die Werte werden vom Host übergeben, wenn der Workflow aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5525b-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="5525b-189">So hosten Sie die Policy-Aktivität mithilfe eines vom Workflow-Designer erstellten Workflows</span><span class="sxs-lookup"><span data-stu-id="5525b-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="5525b-190">Mit der rechten Maustaste **"Workflow1.xaml"** in **Projektmappen-Explorer** , und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="5525b-191">Klicken Sie zur Bestätigung auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="5525b-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="5525b-192">Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** .</span><span class="sxs-lookup"><span data-stu-id="5525b-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="5525b-193">Erweitern Sie die **Visual C#-Elemente** Knoten, und wählen **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="5525b-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="5525b-194">Wählen Sie **Aktivität** aus der **Visual C#-Elemente** Liste.</span><span class="sxs-lookup"><span data-stu-id="5525b-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="5525b-195">Typ `DiscountWorkflow` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="5525b-196">Klicken Sie auf die **Argumente** Schaltfläche auf die links unten im Workflow-Designer zum Anzeigen der **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="5525b-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="5525b-197">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="5525b-198">Typ `Subtotal` in der **Namen** wählen Sie im **In** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5525b-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5525b-199">Wenn **doppelte** befindet sich nicht in der **Argumenttyp** Dropdown-Liste **nach Typen suchen...** , Typ `System.Double` in der **Typnamen** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="5525b-200">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="5525b-201">Typ `DiscountPercent` in der **Namen** wählen Sie im **Out** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5525b-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="5525b-202">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="5525b-203">Typ `Total` in der **Namen** wählen Sie im **Out** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5525b-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="5525b-204">Klicken Sie auf die **Argumente** Schaltfläche links unten im Workflow-Designer schließen auf die **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="5525b-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="5525b-205">Ziehen Sie eine **Sequenz** Aktivität aus der **Control Flow** Teil der **Toolbox** und legen ihn auf die Oberfläche des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="5525b-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="5525b-206">Ziehen Sie ein **Interop** Aktivität aus der **Migration** Teil der **Toolbox** und legen Sie sie in der **Sequenz** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5525b-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="5525b-207">Klicken Sie auf die **Interop** Aktivität auf die **klicken Sie auf Durchsuchen...**</span><span class="sxs-lookup"><span data-stu-id="5525b-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="5525b-208">beschriften, **DiscountCalculator** in der **Typnamen** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5525b-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5525b-209">Wenn dem Workflow die <xref:System.Activities.Statements.Interop>-Aktivität hinzugefügt wird und der `DiscountCalculator`-Typ als <xref:System.Activities.Statements.Interop.ActivityType%2A> angegeben wird, macht die <xref:System.Activities.Statements.Interop>-Aktivität drei <xref:System.Activities.ArgumentDirection.In>-Argumente und drei <xref:System.Activities.ArgumentDirection.Out>-Argumente verfügbar. Diese stellen die drei öffentlichen Eigenschaften der `DiscountCalculator`-Aktivität dar.</span><span class="sxs-lookup"><span data-stu-id="5525b-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="5525b-210">Die <xref:System.Activities.ArgumentDirection.In> Argumente haben den gleichen Namen wie die drei öffentlichen Eigenschaften und die drei <xref:System.Activities.ArgumentDirection.Out> -Argumente haben den gleichen Namen mit **Out** des Eigenschaftennamens angefügt.</span><span class="sxs-lookup"><span data-stu-id="5525b-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="5525b-211">In den folgenden Schritten werden die in den vorherigen Schritten erstellten Workflowargumente an die Argumente der <xref:System.Activities.Statements.Interop>-Aktivität gebunden.</span><span class="sxs-lookup"><span data-stu-id="5525b-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="5525b-212">Typ `DiscountPercent` in der **VB-Ausdruck eingeben** Feld rechts neben der **DiscountPercentOut** -Eigenschaft, und drücken Sie TAB.</span><span class="sxs-lookup"><span data-stu-id="5525b-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="5525b-213">Typ `Subtotal` in der **VB-Ausdruck eingeben** Feld rechts neben der **Subtotal** -Eigenschaft, und drücken Sie TAB.</span><span class="sxs-lookup"><span data-stu-id="5525b-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="5525b-214">Typ `Total` in der **VB-Ausdruck eingeben** Feld rechts neben der **TotalOut** -Eigenschaft, und drücken Sie TAB.</span><span class="sxs-lookup"><span data-stu-id="5525b-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="5525b-215">Mit der rechten Maustaste **"Program.cs"** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5525b-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="5525b-216">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5525b-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="5525b-217">Kommentieren Sie den Aufruf der `CalculateDiscountInCode`-Methode in der `Main`-Methode aus, und fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="5525b-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5525b-218">Wenn Sie das oben beschriebene Verfahren nicht ausgeführt haben und der `Main`-Standardcode vorhanden ist, ersetzen Sie den Inhalt von `Main` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5525b-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="5525b-219">Erstellen Sie in der `Program`-Klasse eine neue Methode namens `CalculateDiscountUsingDesignerWorkflow`, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="5525b-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="5525b-220">Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5525b-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="5525b-221">Ändern Sie den Wert von `Subtotal` im folgenden Code, um eine andere `SubtotalValue`-Menge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5525b-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="5525b-222">Übersicht über die Regelfunktionen</span><span class="sxs-lookup"><span data-stu-id="5525b-222">Rules Features Overview</span></span>  
 <span data-ttu-id="5525b-223">Das [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Regelmodul bietet Hilfe bei der prioritätsbasierten Verarbeitung von Regeln, wobei Vorwärtsverkettung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5525b-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="5525b-224">Regeln können für ein einzelnes Element oder für die Elemente einer Auflistung ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5525b-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="5525b-225">Eine Übersicht über Regeln und Informationen zu einer bestimmten Regelfunktionalität finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5525b-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="5525b-226">Regelfunktionen</span><span class="sxs-lookup"><span data-stu-id="5525b-226">Rules Feature</span></span>|<span data-ttu-id="5525b-227">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="5525b-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="5525b-228">Übersicht über Regeln</span><span class="sxs-lookup"><span data-stu-id="5525b-228">Rules Overview</span></span>|[<span data-ttu-id="5525b-229">Einführung in das Windows Workflow Foundation-Regelmodul</span><span class="sxs-lookup"><span data-stu-id="5525b-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="5525b-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="5525b-230">RuleSet</span></span>|<span data-ttu-id="5525b-231">[Verwenden von RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) und <xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="5525b-231">[Using RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="5525b-232">Auswertung von Regeln</span><span class="sxs-lookup"><span data-stu-id="5525b-232">Evaluation of Rules</span></span>|[<span data-ttu-id="5525b-233">Regelauswertung in RuleSets</span><span class="sxs-lookup"><span data-stu-id="5525b-233">Rules Evaluation in RuleSets</span></span>](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="5525b-234">Regelverkettung</span><span class="sxs-lookup"><span data-stu-id="5525b-234">Rules Chaining</span></span>|<span data-ttu-id="5525b-235">[Vorwärtsverkettung Steuerelement](http://go.microsoft.com/fwlink/?LinkId=178518) und [Vorwärtsverketten von Regeln](http://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="5525b-235">[Forward Chaining Control](http://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](http://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="5525b-236">Verarbeiten von Auflistungen in Regeln</span><span class="sxs-lookup"><span data-stu-id="5525b-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="5525b-237">Verarbeiten von Auflistungen in Regeln</span><span class="sxs-lookup"><span data-stu-id="5525b-237">Processing Collections in Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="5525b-238">Verwenden der PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="5525b-238">Using the PolicyActivity</span></span>|<span data-ttu-id="5525b-239">[Verwenden der PolicyActivity-Aktivität](http://go.microsoft.com/fwlink/?LinkId=178521) und <xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="5525b-239">[Using the PolicyActivity Activity](http://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="5525b-240">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] erstellte Workflows verwenden nicht alle Regelfunktionen, die von [!INCLUDE[wf1](../../../includes/wf1-md.md)] bereitgestellt werden, z. B. deklarative Aktivitätsbedingungen und Bedingungsaktivitäten wie das <xref:System.Workflow.Activities.ConditionedActivityGroup>-Objekt und das <xref:System.Workflow.Activities.ReplicatorActivity>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5525b-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="5525b-241">Bei Bedarf ist diese Funktionalität für Workflows verfügbar, die mit [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5525b-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="5525b-242">Weitere Informationen finden Sie unter [Migrationsanleitung](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="5525b-242">For more information, see [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
