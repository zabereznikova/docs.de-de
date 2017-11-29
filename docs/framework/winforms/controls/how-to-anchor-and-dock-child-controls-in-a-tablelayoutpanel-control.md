---
title: 'Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement'
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
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15a725f7a5a4b61f826756c4c3f0d2a20c8a5011
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="4642f-102">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4642f-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="4642f-103">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement unterstützt die <xref:System.Windows.Forms.Control.Anchor%2A>- und die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft in seinen untergeordneten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="4642f-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="4642f-104">So richten Sie ein untergeordnetes Steuerelement in einer TableLayoutPanel-Zelle aus</span><span class="sxs-lookup"><span data-stu-id="4642f-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="4642f-105">Erstellen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="4642f-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2.  <span data-ttu-id="4642f-106">Legen Sie den Wert, der die <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> und <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> Eigenschaften **1**.</span><span class="sxs-lookup"><span data-stu-id="4642f-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3.  <span data-ttu-id="4642f-107">Erstellen Sie ein <xref:System.Windows.Forms.Button>-Steuerelement im <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4642f-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="4642f-108">Das <xref:System.Windows.Forms.Button> nimmt die obere linke Ecke der Zelle ein.</span><span class="sxs-lookup"><span data-stu-id="4642f-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4.  <span data-ttu-id="4642f-109">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Left`.</span><span class="sxs-lookup"><span data-stu-id="4642f-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="4642f-110">Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es sich am linken Rand der Zelle ausrichtet.</span><span class="sxs-lookup"><span data-stu-id="4642f-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4642f-111">Dieses Verhalten weicht vom Verhalten anderer Containersteuerelemente ab.</span><span class="sxs-lookup"><span data-stu-id="4642f-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="4642f-112">Bei anderen Containersteuerelementen wird das untergeordnete Steuerelement nicht verschoben, wenn die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft festgelegt wird, und der Abstand zwischen dem verankerten Steuerelement und der Grenze des übergeordneten Containers ist zum Zeitpunkt der Festlegung der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft fixiert.</span><span class="sxs-lookup"><span data-stu-id="4642f-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5.  <span data-ttu-id="4642f-113">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="4642f-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="4642f-114">Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es die ober linke Ecke der Zelle einnimmt.</span><span class="sxs-lookup"><span data-stu-id="4642f-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6.  <span data-ttu-id="4642f-115">Wiederholen Sie Schritt 5 mit einem Wert von `Top, Right` zum Verschieben der <xref:System.Windows.Forms.Button> Steuerelement in der oberen rechten Ecke der Zelle.</span><span class="sxs-lookup"><span data-stu-id="4642f-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="4642f-116">Wiederholen Sie diesen Schritt mit den Werten `Bottom, Left` und `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="4642f-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="4642f-117">So strecken Sie ein untergeordnetes Steuerelement in einer TableLayoutPanel-Zelle</span><span class="sxs-lookup"><span data-stu-id="4642f-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="4642f-118">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="4642f-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="4642f-119">Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so angepasst, dass es die gesamte Breite der Zelle einnimmt.</span><span class="sxs-lookup"><span data-stu-id="4642f-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4642f-120">Dieses Verhalten weicht vom Verhalten anderer Containersteuerelemente ab.</span><span class="sxs-lookup"><span data-stu-id="4642f-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="4642f-121">In anderen Containersteuerelementen wird das untergeordnete Steuerelement nicht angepasst, wenn die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaftensatz auf `Left, Right` oder `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="4642f-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2.  <span data-ttu-id="4642f-122">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="4642f-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="4642f-123">Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so angepasst, dass es die gesamte Höhe der Zelle einnimmt.</span><span class="sxs-lookup"><span data-stu-id="4642f-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3.  <span data-ttu-id="4642f-124">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="4642f-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="4642f-125">Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so geändert, dass es die gesamte Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="4642f-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4.  <span data-ttu-id="4642f-126">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `None`.</span><span class="sxs-lookup"><span data-stu-id="4642f-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="4642f-127">Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird geändert, und es wird mittig in der Zelle positioniert.</span><span class="sxs-lookup"><span data-stu-id="4642f-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5.  <span data-ttu-id="4642f-128">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="4642f-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="4642f-129">Das <xref:System.Windows.Forms.Button>-Steuerelement wird so verschoben, dass es sich am linken Rand der Zelle ausrichtet.</span><span class="sxs-lookup"><span data-stu-id="4642f-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="4642f-130">Das <xref:System.Windows.Forms.Button>-Steuerelement behält seine Breite, aber seine Höhe wird so angepasst, dass es die gesamte Zellenhöhe einnimmt.</span><span class="sxs-lookup"><span data-stu-id="4642f-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4642f-131">Dies ist dasselbe Verhalten, das in anderen Containersteuerelementen auftritt.</span><span class="sxs-lookup"><span data-stu-id="4642f-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6.  <span data-ttu-id="4642f-132">Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="4642f-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="4642f-133">Die Größe des <xref:System.Windows.Forms.Button>-Steuerelements wird so geändert, dass es die gesamte Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="4642f-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4642f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4642f-134">Example</span></span>  
 <span data-ttu-id="4642f-135">Die folgende Abbildung zeigt fünf Schaltflächen, die in fünf separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen verankert sind.</span><span class="sxs-lookup"><span data-stu-id="4642f-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="4642f-136">![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="4642f-136">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="4642f-137">Die folgende Abbildung zeigt vier Schaltflächen, die in den Ecken von vier separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen verankert sind.</span><span class="sxs-lookup"><span data-stu-id="4642f-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="4642f-138">![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="4642f-138">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="4642f-139">Die folgende Abbildung zeigt drei Schaltflächen, die durch die Verankerung in drei separaten <xref:System.Windows.Forms.TableLayoutPanel>-Zellen gestreckt wurden.</span><span class="sxs-lookup"><span data-stu-id="4642f-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="4642f-140">![TableLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="4642f-140">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="4642f-141">Das folgende Codebeispiel veranschaulicht alle Kombinationen aus <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4642f-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4642f-142">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4642f-142">Compiling the Code</span></span>  
 <span data-ttu-id="4642f-143">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4642f-143">This example requires:</span></span>  
  
-   <span data-ttu-id="4642f-144">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="4642f-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4642f-145">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4642f-145">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4642f-146">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="4642f-146">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="4642f-147">Siehe auch: [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4642f-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4642f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4642f-148">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="4642f-149">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4642f-149">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
