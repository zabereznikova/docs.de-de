---
title: 'Gewusst wie: Erben von der Control-Klasse'
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
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bdc4a5c7f721fd350f5c604d4529f05afd62a42c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="31545-102">Gewusst wie: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="31545-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="31545-103">Wenn Sie ein vollständig benutzerdefiniertes Steuerelement für die Verwendung in einem Windows Form erstellen möchten, sollten Sie erben von der <xref:System.Windows.Forms.Control> Klasse.</span><span class="sxs-lookup"><span data-stu-id="31545-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="31545-104">Beim Erben von der <xref:System.Windows.Forms.Control> Klasse erfordert, dass Sie ausführen, Planung und Implementierung bereit, sondern auch Sie mit der größten Palette von Optionen.</span><span class="sxs-lookup"><span data-stu-id="31545-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="31545-105">Beim Erben von <xref:System.Windows.Forms.Control>, Sie erben die Basisfunktionalität, die Steuerelemente, die verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31545-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="31545-106">Die Funktionalität, die eine inhärente Eigenschaft der <xref:System.Windows.Forms.Control> Klasse behandelt Benutzereingaben über die Tastatur und Maus, definiert die Grenzen und die Größe des Steuerelements stellt ein Windows-Handle und Meldungsbehandlung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="31545-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="31545-107">Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion.</span><span class="sxs-lookup"><span data-stu-id="31545-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="31545-108">Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="31545-108">You must provide all of these aspects through custom code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31545-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="31545-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="31545-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="31545-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="31545-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="31545-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-custom-control"></a><span data-ttu-id="31545-112">So erstellen Sie ein benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="31545-112">To create a custom control</span></span>  
  
1.  <span data-ttu-id="31545-113">Erstellen Sie ein neues **Windows-Anwendung** oder **Windows-Steuerelementbibliothek**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="31545-113">Create a new **Windows Application** or **Windows Control Library** project.</span></span>  
  
2.  <span data-ttu-id="31545-114">Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="31545-114">From the **Project** menu, choose **Add Class**.</span></span>  
  
3.  <span data-ttu-id="31545-115">Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.</span><span class="sxs-lookup"><span data-stu-id="31545-115">In the **Add New Item** dialog box, click **Custom Control**.</span></span>  
  
     <span data-ttu-id="31545-116">Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="31545-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="31545-117">Drücken Sie F7, um den**Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="31545-117">Press F7 to open the **Code Editor** for your custom control.</span></span>  
  
5.  <span data-ttu-id="31545-118">Suchen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, die mit Ausnahme von einem Aufruf von leer sein wird die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="31545-118">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
6.  <span data-ttu-id="31545-119">Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.</span><span class="sxs-lookup"><span data-stu-id="31545-119">Modify the code to incorporate any custom painting you want for your control.</span></span>  
  
     <span data-ttu-id="31545-120">Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="31545-120">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
7.  <span data-ttu-id="31545-121">Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31545-121">Implement any custom methods, properties, or events that your control will incorporate.</span></span>  
  
8.  <span data-ttu-id="31545-122">Speichern und testen Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="31545-122">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31545-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31545-123">See Also</span></span>  
 [<span data-ttu-id="31545-124">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="31545-124">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="31545-125">Vorgehensweise: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="31545-125">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="31545-126">Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="31545-126">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="31545-127">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31545-127">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="31545-128">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31545-128">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="31545-129">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="31545-129">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
