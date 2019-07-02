---
title: Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506096"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="ece0b-102">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ece0b-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="ece0b-103">Benutzerdefinierte Zeichnen von Steuerelementen ist einer der zahlreichen komplizierteren Aufgaben, die leicht gemacht, die von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ece0b-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="ece0b-104">Wenn Sie ein benutzerdefiniertes Steuerelement erstellen zu können, stehen Ihnen viele Optionen in Bezug auf die grafische Darstellung des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ece0b-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="ece0b-105">Wenn Sie ein Steuerelement erstellen, die von erbt die `Control`, müssen Sie Code, der das Steuerelement zum Rendern der grafischen Darstellung ermöglicht angeben.</span><span class="sxs-lookup"><span data-stu-id="ece0b-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="ece0b-106">Wenn Sie ein Benutzersteuerelement erstellen durch Erben von der `UserControl`, oder werden erben von einer Windows Forms-Steuerelemente, können Sie außer Kraft setzen die standardmäßige grafische Darstellung und bieten Sie Ihren eigenen Grafikcode.</span><span class="sxs-lookup"><span data-stu-id="ece0b-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="ece0b-107">Wenn Sie benutzerdefiniertes Rendering für die konstituierenden Steuerelemente bereitstellen möchten eine `UserControl` Sie erstellen, die Optionen stärker eingeschränkt werden, aber immer noch eine Vielzahl von grafischen Möglichkeiten für Ihre Steuerelemente und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ece0b-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ece0b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ece0b-108">In This Section</span></span>  
 [<span data-ttu-id="ece0b-109">Wiedergeben eines Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ece0b-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="ece0b-110">Zeigt, wie die Logik zu programmieren, die einem Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ece0b-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="ece0b-111">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ece0b-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="ece0b-112">Bietet eine Übersicht über die Schritte zum Schreiben und das Überschreiben von Code für das Steuerelement rendern.</span><span class="sxs-lookup"><span data-stu-id="ece0b-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="ece0b-113">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ece0b-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="ece0b-114">Beschreibt, wie benutzerdefinierte Rendering-Code für konstituierende Steuerelemente in Ihre Steuerelemente und Formulare zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="ece0b-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="ece0b-115">Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ece0b-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="ece0b-116">Zeigt, wie die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft aus-und Einblenden eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ece0b-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="ece0b-117">Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund</span><span class="sxs-lookup"><span data-stu-id="ece0b-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="ece0b-118">Zeigt, wie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode, um eine Hintergrundfarbe zu erstellen, die nicht transparenten, transparente oder teilweise transparent ist.</span><span class="sxs-lookup"><span data-stu-id="ece0b-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="ece0b-119">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="ece0b-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="ece0b-120">Zeigt, wie zum Rendern von Steuerelementen mit visuellen Stilen in Betriebssystemen, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ece0b-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ece0b-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="ece0b-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="ece0b-122">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ece0b-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="ece0b-123">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ece0b-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="ece0b-124">Wird diese Methode beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ece0b-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ece0b-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ece0b-125">Related Sections</span></span>  
 [<span data-ttu-id="ece0b-126">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="ece0b-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="ece0b-127">Stellt die GDI +-Grafikfunktionen aus einer Visual Studio-Perspektive, und enthält Links zu weiteren Informationen.</span><span class="sxs-lookup"><span data-stu-id="ece0b-127">Introduces GDI+ graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="ece0b-128">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="ece0b-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="ece0b-129">Beschreibt die Arten von benutzerdefinierten Steuerelementen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ece0b-129">Describes the kinds of custom controls you can author.</span></span>
