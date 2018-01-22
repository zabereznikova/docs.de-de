---
title: 'Gewusst wie: Erben von der UserControl-Klasse'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eec04e6122f32321c34efe030bfca943baed5bf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="9004d-102">Gewusst wie: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="9004d-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="9004d-103">Sie können ein *Benutzersteuerelement* erstellen, um die Funktionalität einer oder mehrerer Windows Forms-Steuerelemente mit benutzerdefiniertem Code zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9004d-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="9004d-104">Benutzersteuerelemente kombinieren die schnelle Entwicklung von Steuerelementen, die standardmäßige Funktionalität von Windows Forms-Steuerelementen und die Vielseitigkeit von benutzerdefinierten Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="9004d-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="9004d-105">Wenn Sie mit dem Erstellen eines Benutzersteuerelements beginnen, wird ein Designer angezeigt, auf dem Sie die standardmäßigen Windows Forms-Steuerelemente platzieren können.</span><span class="sxs-lookup"><span data-stu-id="9004d-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="9004d-106">Diese Steuerelemente behalten ihre implementierte Funktionalität sowie das Aussehen und Verhalten der Standardsteuerelemente.</span><span class="sxs-lookup"><span data-stu-id="9004d-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="9004d-107">Sobald diese Steuerelemente in das Benutzersteuerelement integriert sind, stehen sie jedoch nicht mehr über Code zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9004d-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="9004d-108">Das Benutzersteuerelement führt seine eigene Grafikausgabe aus und behandelt auch die gesamte grundlegende Funktionalität von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="9004d-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9004d-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="9004d-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9004d-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9004d-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9004d-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="9004d-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="9004d-112">So erstellen Sie ein benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9004d-112">To create a user control</span></span>  
  
1.  <span data-ttu-id="9004d-113">Erstellen Sie ein neues eines **Windows-Steuerelementbibliothek**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="9004d-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="9004d-114">Ein neues Projekt mit einem leeren Benutzersteuerelement wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="9004d-114">A new project is created with a blank user control.</span></span>  
  
2.  <span data-ttu-id="9004d-115">Ziehen Sie Steuerelemente von der Registerkarte **Windows Forms** der **Toolbox** auf den Designer.</span><span class="sxs-lookup"><span data-stu-id="9004d-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3.  <span data-ttu-id="9004d-116">Diese Steuerelemente sollten so positioniert und entworfen werden, wie Sie im fertig gestellten Steuerelement angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9004d-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="9004d-117">Wenn Sie möchten, dass Entwickler auf die konstituierenden Steuerelemente zugreifen können, müssen Sie diese als öffentlich deklarieren oder Eigenschaften des konstituierenden Steuerelements einzeln verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="9004d-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="9004d-118">Einzelheiten finden Sie unter [Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9004d-118">For details, see [How to: Expose Properties of Constituent Controls](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4.  <span data-ttu-id="9004d-119">Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9004d-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5.  <span data-ttu-id="9004d-120">Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.</span><span class="sxs-lookup"><span data-stu-id="9004d-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="9004d-121">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="9004d-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9004d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9004d-122">See Also</span></span>  
 [<span data-ttu-id="9004d-123">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="9004d-123">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="9004d-124">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="9004d-124">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="9004d-125">Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9004d-125">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="9004d-126">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9004d-126">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="9004d-127">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9004d-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="9004d-128">Gewusst wie: Testen des Laufzeitverhaltens eines UserControl</span><span class="sxs-lookup"><span data-stu-id="9004d-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
