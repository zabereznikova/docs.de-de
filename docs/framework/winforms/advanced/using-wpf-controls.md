---
title: Verwenden von WPF-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: be925bdceea3dd01c568d85fe025d6e037066454
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170469"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="7e0e8-102">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7e0e8-102">Using WPF Controls</span></span>
<span data-ttu-id="7e0e8-103">Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="7e0e8-104">Obwohl diese beiden Technologien für andere Ansicht sind, zusammenarbeiten sie reibungslos.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="7e0e8-105">Der Windows Forms-Designer stellt eine visuelle entwurfsumgebung zum Hosten von Windows Presentation Foundation-Steuerelementen bereit.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="7e0e8-106">Ein WPF-Steuerelement gehostet wird, von einem speziellen Windows Forms-Steuerelement mit dem Namen <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="7e0e8-107">Mit diesem Steuerelement können das WPF-Steuerelement zur Teilnahme an das Layout des Formulars und zum Empfangen von Nachrichten von Tastatur und Maus.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="7e0e8-108">Sie können zur Entwurfszeit Anordnen der <xref:System.Windows.Forms.Integration.ElementHost> steuern, wie Sie jedes Windows Forms-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="7e0e8-109">Sie können auch Windows Forms-Steuerelementen in WPF-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="7e0e8-110">Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7e0e8-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e0e8-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7e0e8-111">In This Section</span></span>  
 [<span data-ttu-id="7e0e8-112">Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7e0e8-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="7e0e8-113">Zeigt, wie Sie ein Windows Presentation Foundation-Steuerelement in Windows Forms zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="7e0e8-114">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7e0e8-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="7e0e8-115">Veranschaulicht, wie die Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, Anordnen von Windows Presentation Foundation-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>
  
 [<span data-ttu-id="7e0e8-116">Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7e0e8-116">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="7e0e8-117">Zeigt, wie eine Windows Presentation Foundation-Steuerelement, für die Verwendung in Windows Forms-basierte Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>
  
 [<span data-ttu-id="7e0e8-118">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7e0e8-118">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="7e0e8-119">Zeigt, wie die Windows Presentation Foundation-Steuerelementtypen auswählen, die Sie in Ihrem Formular anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="7e0e8-120">Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt</span><span class="sxs-lookup"><span data-stu-id="7e0e8-120">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="7e0e8-121">Zeigt den Workflow zwischen dem Windows Forms-Designer und die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] zum Anwenden von Stilen für Windows Presentation Foundation-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7e0e8-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="7e0e8-122">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="7e0e8-123">Beschreibt eine Klasse, die Sie zum Hosten von Windows Presentation Foundation-Steuerelementen in Windows Forms-basierten Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="7e0e8-124">Beschreibt eine Klasse, die Sie zum Hosten von Windows Forms-Steuerelementen in der Windows Presentation Foundation-basierte Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7e0e8-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7e0e8-125">Related Sections</span></span>  
 [<span data-ttu-id="7e0e8-126">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="7e0e8-126">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="7e0e8-127">Beschreibt die Interoperation zwischen der Windows Presentation Foundation und Windows Forms-Technologien.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="7e0e8-128">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e0e8-128">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 <span data-ttu-id="7e0e8-129">Beschreibt, wie Windows Presentation Foundation-Steuerelemente in Visual Studio entwerfen.</span><span class="sxs-lookup"><span data-stu-id="7e0e8-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
