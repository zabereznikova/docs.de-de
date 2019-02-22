---
title: 'Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: b2ccbfaf8305270116e3a85578e3e560ed0b4836
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584212"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="419d0-102">Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="419d0-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="419d0-103">Zusammengesetzte Steuerelemente können auf viele Arten eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="419d0-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="419d0-104">Sie können sie als Teil eines Desktopanwendungsprojekts von Windows erstellen und nur für Formulare im Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="419d0-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="419d0-105">Oder Sie können sie in einem Windows-Steuerelementbibliothek-Projekt erstellen, das Projekt in eine Assembly kompilieren und die Steuerelemente in anderen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="419d0-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="419d0-106">Sie können sogar von ihnen erben und visuelle Vererbung verwenden, um sie schnell für besondere Zwecke anzupassen.</span><span class="sxs-lookup"><span data-stu-id="419d0-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="419d0-107">Wenn Sie ein zusammengesetztes Steuerelement erstellen möchten, das in Web Forms verwendet werden soll, sollten Sie [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)) lesen.</span><span class="sxs-lookup"><span data-stu-id="419d0-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
>   
>  <span data-ttu-id="419d0-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="419d0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="419d0-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="419d0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="419d0-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="419d0-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="419d0-111">So erstellen Sie ein zusammengesetztes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="419d0-111">To author a composite control</span></span>  
  
1.  <span data-ttu-id="419d0-112">Öffnen Sie ein neues **Windows-Anwendungsprojekt** namens `DemoControlHost`.</span><span class="sxs-lookup"><span data-stu-id="419d0-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2.  <span data-ttu-id="419d0-113">Klicken Sie im Menü **Projekt** auf **Benutzersteuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="419d0-113">On the **Project** menu, click **Add User Control**.</span></span>  
  
3.  <span data-ttu-id="419d0-114">Geben Sie im Dialogfeld **Neues Element hinzufügen** der Klassendatei (VB- oder CS-Datei) den Namen, den das zusammengesetzte Steuerelement tragen soll.</span><span class="sxs-lookup"><span data-stu-id="419d0-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4.  <span data-ttu-id="419d0-115">Wählen Sie die **hinzufügen** klicken, um die Klassendatei für das zusammengesetzte Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="419d0-115">Select the **Add** button to create the class file for the composite control.</span></span>  
  
5.  <span data-ttu-id="419d0-116">Fügen Sie Steuerelemente aus der **Toolbox** zur Oberfläche des zusammengesetzten Steuerelements hinzu.</span><span class="sxs-lookup"><span data-stu-id="419d0-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6.  <span data-ttu-id="419d0-117">Platzieren Sie Code in Ereignisprozeduren, um Ereignisse zu behandeln, die vom zusammengesetzten Steuerelement oder konstituierenden Steuerelementen ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="419d0-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7.  <span data-ttu-id="419d0-118">Schließen Sie den Designer für das zusammengesetzte Steuerelement, und speichern Sie die Datei, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="419d0-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8.  <span data-ttu-id="419d0-119">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="419d0-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="419d0-120">Das Projekt muss erstellt werden, damit benutzerdefinierte Steuerelemente in der **Toolbox** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="419d0-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="419d0-121">Verwenden Sie die Registerkarte **DemoControlHost** der **Toolbox**, um Instanzen Ihres Steuerelements zu `Form1` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="419d0-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="419d0-122">So erstellen Sie eine Steuerelementklassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="419d0-122">To author a control class library</span></span>  
  
1.  <span data-ttu-id="419d0-123">Öffnen Sie ein neues **Windows-Steuerelementbibliothek**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="419d0-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="419d0-124">Standardmäßig enthält das Projekt ein zusammengesetztes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="419d0-124">By default, the project contains a composite control.</span></span>  
  
2.  <span data-ttu-id="419d0-125">Fügen Sie Steuerelemente und Code wie im beschriebenen Verfahren hinzu.</span><span class="sxs-lookup"><span data-stu-id="419d0-125">Add controls and code as described in the procedure above.</span></span>  
  
3.  <span data-ttu-id="419d0-126">Wählen Sie ein Steuerelement aus, das von vererbenden Klassen nicht geändert werden soll, und legen Sie die Eigenschaft des **Modifizierers** auf **Privat** fest.</span><span class="sxs-lookup"><span data-stu-id="419d0-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4.  <span data-ttu-id="419d0-127">Erstellen Sie die DLL.</span><span class="sxs-lookup"><span data-stu-id="419d0-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="419d0-128">So erben Sie in einer Steuerelementklassenbibliothek von einem zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="419d0-128">To inherit from a composite control in a control class library</span></span>  
  
1.  <span data-ttu-id="419d0-129">Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und wählen Sie **Neues Projekt** aus, um ein neues **Windows-Anwendungs**-Projekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="419d0-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2.  <span data-ttu-id="419d0-130">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** für das neue Projekt, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="419d0-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3.  <span data-ttu-id="419d0-131">Wählen Sie die Registerkarte **Projekte** aus, und doppelklicken Sie auf Ihr Steuerelementbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="419d0-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4.  <span data-ttu-id="419d0-132">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="419d0-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="419d0-133">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Steuerelementbibliotheksprojekt, und wählen Sie dann **Neues Element hinzufügen** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="419d0-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6.  <span data-ttu-id="419d0-134">Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** aus dem Dialogfeld **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="419d0-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7.  <span data-ttu-id="419d0-135">Doppelklicken Sie im Dialogfeld **Vererbungsauswahl** auf das Steuerelement, von dem Sie erben möchten.</span><span class="sxs-lookup"><span data-stu-id="419d0-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="419d0-136">Ein neues Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="419d0-136">A new control is added to your project.</span></span>  
  
8.  <span data-ttu-id="419d0-137">Öffnen Sie den visuellen Designer für das neue Steuerelement, und fügen Sie zusätzliche konstituierende Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="419d0-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="419d0-138">Die konstituierenden Steuerelemente, die vom zusammengesetzten Steuerelement geerbt wurden, werden in Ihrer DLL angezeigt und Sie können die Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Öffentlich** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="419d0-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="419d0-139">Sie können keine Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Privat** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="419d0-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419d0-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="419d0-140">See also</span></span>
- [<span data-ttu-id="419d0-141">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="419d0-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="419d0-142">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit visuellen ElementC#</span><span class="sxs-lookup"><span data-stu-id="419d0-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="419d0-143">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="419d0-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="419d0-144">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit visuellen ElementC#</span><span class="sxs-lookup"><span data-stu-id="419d0-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="419d0-145">Empfehlungen zum Typ von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="419d0-145">Control Type Recommendations</span></span>](../../../../docs/framework/winforms/controls/control-type-recommendations.md)
- [<span data-ttu-id="419d0-146">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="419d0-146">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="419d0-147">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="419d0-147">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
