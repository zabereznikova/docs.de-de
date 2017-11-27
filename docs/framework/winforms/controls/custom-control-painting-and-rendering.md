---
title: Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: babf3d235f4cca61ad6d0e5fdc4e6b6146c7d060
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="86457-102">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="86457-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="86457-103">Benutzerdefiniertes Zeichnen von Steuerelementen ist einer der zahlreichen komplizierten Aufgaben, die leicht, von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86457-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="86457-104">Wenn Sie ein benutzerdefiniertes Steuerelement zu erstellen, stehen Ihnen viele Optionen zur grafischen Darstellung des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="86457-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="86457-105">Wenn Sie ein Steuerelement erstellen, die von erben die `Control`, müssen Sie Code, der das Steuerelement zum Rendern der grafischen Darstellung ermöglicht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86457-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="86457-106">Wenn Sie ein Benutzersteuerelement erstellen durch Erben von der `UserControl`, oder erben werden aus einer Windows Forms-Steuerelemente, können Sie außer Kraft setzen die standardmäßige grafische Darstellung und fügen Sie eigenen Code Grafiken.</span><span class="sxs-lookup"><span data-stu-id="86457-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="86457-107">Wenn Sie benutzerdefiniertes Rendering für die konstituierenden Steuerelemente bereitstellen möchten eine `UserControl` Sie erstellen, die Optionen eingeschränkt werden, aber weiterhin eine Breite Palette von grafischen Möglichkeiten für Steuerelemente und Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="86457-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86457-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="86457-108">In This Section</span></span>  
 [<span data-ttu-id="86457-109">Wiedergeben eines Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="86457-109">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 <span data-ttu-id="86457-110">Veranschaulicht das Programmieren der Logik, die ein Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86457-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="86457-111">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="86457-111">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 <span data-ttu-id="86457-112">Bietet einen Überblick über die Schritte zum Schreiben und überschreiben Code zum Rendern des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="86457-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="86457-113">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="86457-113">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 <span data-ttu-id="86457-114">Beschreibt, wie benutzerdefinierte Renderingcodes für konstituierende Steuerelemente in Ihrer Benutzersteuerelementen und-Formularen implementieren.</span><span class="sxs-lookup"><span data-stu-id="86457-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="86457-115">Gewusst wie: Ausblenden des Steuerelements zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="86457-115">How to: Make Your Control Invisible at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="86457-116">Zeigt, wie die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft aus-und Einblenden eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="86457-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="86457-117">Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="86457-117">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="86457-118">Zeigt, wie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode, um eine Hintergrundfarbe zu erstellen, die nicht transparenten, transparent oder teilweise transparent ist.</span><span class="sxs-lookup"><span data-stu-id="86457-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="86457-119">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="86457-119">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="86457-120">Zeigt, wie zum Rendern von Steuerelementen mit visuellen Stilen in Betriebssystemen, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="86457-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="86457-121">Verweis</span><span class="sxs-lookup"><span data-stu-id="86457-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="86457-122">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="86457-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="86457-123">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="86457-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="86457-124">Wird diese Methode beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86457-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="86457-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="86457-125">Related Sections</span></span>  
 [<span data-ttu-id="86457-126">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="86457-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="86457-127">Führt [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Grafikfunktionen aus einer Visual Studio-Perspektive und enthält Links zu weiteren Informationen.</span><span class="sxs-lookup"><span data-stu-id="86457-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="86457-128">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="86457-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="86457-129">Beschreibt die Arten von benutzerdefinierten Steuerelementen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="86457-129">Describes the kinds of custom controls you can author.</span></span>
