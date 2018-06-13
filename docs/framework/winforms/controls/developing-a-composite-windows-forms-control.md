---
title: Entwickeln eines zusammengesetzten Windows Forms-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: dc038e5a1858025007ef737397521bfea1b93b97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528287"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="9e97c-102">Entwickeln eines zusammengesetzten Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="9e97c-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="9e97c-103">Sie können ein zusammengesetztes Windows Forms-Steuerelement entwickeln, indem Sie andere Windows Forms-Steuerelemente kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9e97c-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="9e97c-104">Zusammengesetzte Steuerelemente, die davon Herleiten <xref:System.Web.UI.UserControl> werden als Benutzersteuerelemente bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9e97c-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="9e97c-105">Die Basisklasse, <xref:System.Windows.Forms.UserControl>, ermöglicht Tastaturrouting für die untergeordneten Steuerelemente und stellt damit sicher, dass untergeordnete Steuerelemente den Fokus erhalten können.</span><span class="sxs-lookup"><span data-stu-id="9e97c-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="9e97c-106">Ein Beispiel für ein Benutzersteuerelement, finden Sie unter der <xref:System.Windows.Forms.UserControl> -Beispiel in [wie: Anwenden von Attributen auf Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9e97c-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="9e97c-107">Der Windows Forms-Designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] stellt umfassende Entwurfszeitunterstützung für die Erstellung von Benutzersteuerelementen bereit.</span><span class="sxs-lookup"><span data-stu-id="9e97c-107">The Windows Forms designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] provides rich design-time support for authoring user controls.</span></span>  
  
-   <span data-ttu-id="9e97c-108">[Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-109">[Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-109">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-110">[Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](http://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438)</span><span class="sxs-lookup"><span data-stu-id="9e97c-110">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](http://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438))</span></span>  
  
-   <span data-ttu-id="9e97c-111">[Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-111">[How to: Provide a Toolbox Bitmap for a Control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-112">[Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-112">[How to: Inherit from Existing Windows Forms Controls](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-113">[Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-113">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-114">[Vorgehensweise: Erben von der Control-Klasse](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-114">[How to: Inherit from the Control Class](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-115">[Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-115">[How to: Test the Run-Time Behavior of a UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-116">[Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-116">[How to: Align a Control to the Edges of Forms at Design Time](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-117">[Vorgehensweise: Erben von der UserControl-Klasse](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-117">[How to: Inherit from the UserControl Class](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-118">[Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-118">[How to: Author Controls for Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-119">[Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-119">[How to: Author Composite Controls](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-120">[Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-120">[Walkthrough: Authoring a Composite Control with Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-121">[Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#](http://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f)</span><span class="sxs-lookup"><span data-stu-id="9e97c-121">[Walkthrough: Authoring a Composite Control with Visual C#](http://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f))</span></span>  
  
-   <span data-ttu-id="9e97c-122">[Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-122">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-123">[Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-123">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9e97c-124">[Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="9e97c-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e97c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e97c-125">See Also</span></span>  
 [<span data-ttu-id="9e97c-126">Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e97c-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="9e97c-127">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e97c-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="9e97c-128">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="9e97c-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
