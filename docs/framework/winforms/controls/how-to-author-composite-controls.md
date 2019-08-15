---
title: 'Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 7b0ee8efa62175e2ced2a810ca6dd76e8adc103b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039892"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="397d4-102">Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="397d4-102">How to: Author Composite Controls</span></span>

<span data-ttu-id="397d4-103">Zusammengesetzte Steuerelemente können auf viele Arten eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="397d4-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="397d4-104">Sie können sie als Teil eines Desktopanwendungsprojekts von Windows erstellen und nur für Formulare im Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="397d4-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="397d4-105">Oder Sie können sie in einem Windows-Steuerelementbibliothek-Projekt erstellen, das Projekt in eine Assembly kompilieren und die Steuerelemente in anderen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="397d4-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="397d4-106">Sie können sogar von Ihnen erben und visuelle Vererbung verwenden, um Sie schnell für spezielle Zwecke anzupassen.</span><span class="sxs-lookup"><span data-stu-id="397d4-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

> [!NOTE]
> <span data-ttu-id="397d4-107">Wenn Sie ein zusammengesetztes Steuerelement erstellen möchten, das in Web Forms verwendet werden soll, sollten Sie [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)) lesen.</span><span class="sxs-lookup"><span data-stu-id="397d4-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="397d4-108">So erstellen Sie ein zusammengesetztes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="397d4-108">To author a composite control</span></span>

1. <span data-ttu-id="397d4-109">Erstellen Sie in Visual Studio ein neues **Windows-Anwendungs** Projekt `DemoControlHost`mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="397d4-109">In Visual Studio, create a new **Windows Application** project called `DemoControlHost`.</span></span>

2. <span data-ttu-id="397d4-110">Klicken Sie im Menü **Projekt** auf **Benutzersteuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="397d4-110">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="397d4-111">Geben Sie im Dialogfeld **Neues Element hinzufügen** der Klassendatei (VB- oder CS-Datei) den Namen, den das zusammengesetzte Steuerelement tragen soll.</span><span class="sxs-lookup"><span data-stu-id="397d4-111">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="397d4-112">Wählen Sie die Schaltfläche **Hinzufügen** , um die Klassendatei für das zusammengesetzte Steuerelement zu erstellen</span><span class="sxs-lookup"><span data-stu-id="397d4-112">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="397d4-113">Fügen Sie Steuerelemente aus der **Toolbox** zur Oberfläche des zusammengesetzten Steuerelements hinzu.</span><span class="sxs-lookup"><span data-stu-id="397d4-113">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="397d4-114">Platzieren Sie Code in Ereignisprozeduren, um Ereignisse zu behandeln, die vom zusammengesetzten Steuerelement oder konstituierenden Steuerelementen ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="397d4-114">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="397d4-115">Schließen Sie den Designer für das zusammengesetzte Steuerelement, und speichern Sie die Datei, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="397d4-115">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="397d4-116">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="397d4-116">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="397d4-117">Das Projekt muss erstellt werden, damit benutzerdefinierte Steuerelemente in der **Toolbox** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="397d4-117">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="397d4-118">Verwenden Sie die Registerkarte **DemoControlHost** der **Toolbox**, um Instanzen Ihres Steuerelements zu `Form1` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="397d4-118">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="397d4-119">So erstellen Sie eine Steuerelementklassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="397d4-119">To author a control class library</span></span>

1. <span data-ttu-id="397d4-120">Öffnen Sie ein neues **Windows-Steuerelementbibliothek**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="397d4-120">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="397d4-121">Standardmäßig enthält das Projekt ein zusammengesetztes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="397d4-121">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="397d4-122">Fügen Sie Steuerelemente und Code wie im beschriebenen Verfahren hinzu.</span><span class="sxs-lookup"><span data-stu-id="397d4-122">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="397d4-123">Wählen Sie ein Steuerelement aus, das von vererbenden Klassen nicht geändert werden soll, und legen Sie die Eigenschaft des **Modifizierers** auf **Privat** fest.</span><span class="sxs-lookup"><span data-stu-id="397d4-123">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="397d4-124">Erstellen Sie die DLL.</span><span class="sxs-lookup"><span data-stu-id="397d4-124">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="397d4-125">So erben Sie in einer Steuerelementklassenbibliothek von einem zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="397d4-125">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="397d4-126">Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und wählen Sie **Neues Projekt** aus, um ein neues **Windows-Anwendungs**-Projekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="397d4-126">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="397d4-127">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** für das neue Projekt, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="397d4-127">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="397d4-128">Wählen Sie die Registerkarte **Projekte** aus, und doppelklicken Sie auf Ihr Steuerelementbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="397d4-128">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="397d4-129">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="397d4-129">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="397d4-130">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Steuerelementbibliotheksprojekt, und wählen Sie dann **Neues Element hinzufügen** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="397d4-130">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="397d4-131">Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** aus dem Dialogfeld **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="397d4-131">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="397d4-132">Doppelklicken Sie im Dialogfeld **Vererbungsauswahl** auf das Steuerelement, von dem Sie erben möchten.</span><span class="sxs-lookup"><span data-stu-id="397d4-132">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="397d4-133">Ein neues Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="397d4-133">A new control is added to your project.</span></span>

8. <span data-ttu-id="397d4-134">Öffnen Sie den visuellen Designer für das neue Steuerelement, und fügen Sie zusätzliche konstituierende Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="397d4-134">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="397d4-135">Die konstituierenden Steuerelemente, die vom zusammengesetzten Steuerelement geerbt wurden, werden in Ihrer DLL angezeigt und Sie können die Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Öffentlich** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="397d4-135">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="397d4-136">Sie können keine Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Privat** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="397d4-136">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="397d4-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="397d4-137">See also</span></span>

- [<span data-ttu-id="397d4-138">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="397d4-138">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="397d4-139">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit VisualC#</span><span class="sxs-lookup"><span data-stu-id="397d4-139">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="397d4-140">Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="397d4-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="397d4-141">Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit VisualC#</span><span class="sxs-lookup"><span data-stu-id="397d4-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="397d4-142">Empfehlungen zum Typ von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="397d4-142">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="397d4-143">Vorgehensweise: Steuerelemente für Windows Forms erstellen</span><span class="sxs-lookup"><span data-stu-id="397d4-143">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="397d4-144">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="397d4-144">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
