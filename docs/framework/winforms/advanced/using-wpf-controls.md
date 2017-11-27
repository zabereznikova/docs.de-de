---
title: Verwenden von WPF-Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6fe8fb972f8080bbffeed5db2063d8c0484aec4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="using-wpf-controls"></a><span data-ttu-id="4b2d5-102">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="4b2d5-102">Using WPF Controls</span></span>
<span data-ttu-id="4b2d5-103">Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="4b2d5-104">Obwohl diese zwei unterschiedliche Ansicht Technologien sind, zusammenarbeiten sie reibungslos.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="4b2d5-105">Windows Forms-Designer bietet eine visuelle entwurfsumgebung zum Hosten von Windows Presentation Foundation-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="4b2d5-106">Ein WPF-Steuerelement gehostet wird, von einem speziellen Windows Forms-Steuerelement mit dem Namen <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="4b2d5-107">Dieses Steuerelement ermöglicht das WPF-Steuerelement zur Teilnahme an der das Formularlayout und zum Empfangen von Nachrichten von Tastatur und Maus.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="4b2d5-108">Sie können zur Entwurfszeit Anordnen der <xref:System.Windows.Forms.Integration.ElementHost> steuern, wie Sie jedes Windows Forms-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="4b2d5-109">Sie können auch Windows Forms-Steuerelemente in Ihrer WPF-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="4b2d5-110">Weitere Informationen finden Sie unter [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26).</span><span class="sxs-lookup"><span data-stu-id="4b2d5-110">For more information, see [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b2d5-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4b2d5-111">In This Section</span></span>  
 [<span data-ttu-id="4b2d5-112">Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4b2d5-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="4b2d5-113">Veranschaulicht das Kopieren eines Windows Presentation Foundation-Steuerelements in einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="4b2d5-114">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4b2d5-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="4b2d5-115">Zeigt, wie Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, zum Anordnen von Windows Presentation Foundation-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="4b2d5-116">Exemplarische Vorgehensweise: Ändern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4b2d5-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="4b2d5-117">Zeigt den Workflow zwischen Windows Forms-Designer und der [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zum Ändern von Eigenschaften auf WPF-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="4b2d5-118">Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4b2d5-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="4b2d5-119">Zeigt, wie ein Windows Presentation Foundation-Steuerelement für die Verwendung in Windows Forms-basierten Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="4b2d5-120">Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b2d5-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="4b2d5-121">Zeigt, wie ein Windows Presentation Foundation-Steuerelement von einem Windows Form in eine andere kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="4b2d5-122">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4b2d5-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="4b2d5-123">Zeigt, wie die Windows Presentation Foundation-Steuerelementtypen auswählen, die auf dem Formular angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="4b2d5-124">Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt</span><span class="sxs-lookup"><span data-stu-id="4b2d5-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="4b2d5-125">Zeigt den Workflow zwischen Windows Forms-Designer und der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] zum Anwenden von Stilen auf Steuerelemente für Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4b2d5-126">Verweis</span><span class="sxs-lookup"><span data-stu-id="4b2d5-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="4b2d5-127">Beschreibt eine Klasse, die zum Hosten von Windows Presentation Foundation-Steuerelementen in Windows Forms-basierten Anwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="4b2d5-128">Beschreibt eine Klasse, die Sie zum Hosten von Windows Forms-Steuerelementen in einer Windows Presentation Foundation-basierten Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4b2d5-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4b2d5-129">Related Sections</span></span>  
 [<span data-ttu-id="4b2d5-130">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="4b2d5-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="4b2d5-131">Beschreibt die Interoperation zwischen der Windows Presentation Foundation und Windows Forms-Technologien.</span><span class="sxs-lookup"><span data-stu-id="4b2d5-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="4b2d5-132">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="4b2d5-132">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="4b2d5-133">Beschreibt das Entwerfen von Windows Presentation Foundation-Steuerelementen in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b2d5-133">Describes how to design Windows Presentation Foundation controls in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>
