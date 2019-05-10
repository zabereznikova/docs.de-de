---
title: Verwenden von WPF-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211310"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="a1a0f-102">Verwenden von WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a1a0f-102">Use WPF controls</span></span>

<span data-ttu-id="a1a0f-103">Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="a1a0f-104">Obwohl diese beiden Technologien für andere Ansicht sind, zusammenarbeiten sie reibungslos.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="a1a0f-105">Windows Forms-Designer in Visual Studio bietet eine visuelle entwurfsumgebung zum Hosten von Windows Presentation Foundation-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="a1a0f-106">Ein WPF-Steuerelement gehostet wird, von einem speziellen Windows Forms-Steuerelement mit dem Namen <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="a1a0f-107">Mit diesem Steuerelement können das WPF-Steuerelement zur Teilnahme an das Layout des Formulars und zum Empfangen von Nachrichten von Tastatur und Maus.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="a1a0f-108">Sie können zur Entwurfszeit Anordnen der <xref:System.Windows.Forms.Integration.ElementHost> steuern, wie Sie jedes Windows Forms-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="a1a0f-109">Sie können auch Windows Forms-Steuerelementen in WPF-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="a1a0f-110">Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a1a0f-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a1a0f-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1a0f-111">In This Section</span></span>

<span data-ttu-id="a1a0f-112">[Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="a1a0f-113">Zeigt, wie Sie ein Windows Presentation Foundation-Steuerelement in Windows Forms zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="a1a0f-114">[Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="a1a0f-115">Veranschaulicht, wie die Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, Anordnen von Windows Presentation Foundation-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="a1a0f-116">[Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="a1a0f-117">Zeigt, wie eine Windows Presentation Foundation-Steuerelement, für die Verwendung in Windows Forms-basierte Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="a1a0f-118">[Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="a1a0f-119">Zeigt, wie die Windows Presentation Foundation-Steuerelementtypen auswählen, die Sie in Ihrem Formular anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="a1a0f-120">[Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="a1a0f-121">Zeigt den Workflow zwischen dem Windows Forms-Designer und die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] zum Anwenden von Stilen für Windows Presentation Foundation-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="a1a0f-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="a1a0f-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="a1a0f-123">Beschreibt eine Klasse, die Sie zum Hosten von Windows Presentation Foundation-Steuerelementen in Windows Forms-basierten Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="a1a0f-124">Beschreibt eine Klasse, die Sie zum Hosten von Windows Forms-Steuerelementen in der Windows Presentation Foundation-basierte Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a1a0f-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a1a0f-125">Related sections</span></span>

<span data-ttu-id="a1a0f-126">[Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="a1a0f-127">Beschreibt die Interoperation zwischen der Windows Presentation Foundation und Windows Forms-Technologien.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="a1a0f-128">[Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="a1a0f-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="a1a0f-129">Beschreibt, wie Windows Presentation Foundation-Steuerelemente in Visual Studio entwerfen.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
