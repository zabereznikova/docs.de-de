---
title: Verwenden von WPF-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460696"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="c0c5c-102">Verwenden von WPF-Steuerelementen in Windows Forms-apps</span><span class="sxs-lookup"><span data-stu-id="c0c5c-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="c0c5c-103">Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="c0c5c-104">Obwohl es sich um zwei verschiedene Ansichts Technologien handelt, funktionieren Sie problemlos.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="c0c5c-105">Der Windows Forms-Designer in Visual Studio stellt eine visuelle Entwurfs Umgebung zum Hosting von Windows Presentation Foundation Steuerelementen bereit.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="c0c5c-106">Ein WPF-Steuerelement wird von einem speziellen Windows Forms-Steuerelement gehostet, das <xref:System.Windows.Forms.Integration.ElementHost>heißt.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="c0c5c-107">Mit diesem Steuerelement kann das WPF-Steuerelement am Layout des Formulars teilnehmen und Tastatur-und Maus Meldungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="c0c5c-108">Zur Entwurfszeit können Sie das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement genauso wie jedes beliebige Windows Forms Steuerelement anordnen.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="c0c5c-109">Sie können auch Windows Forms-Steuerelemente in WPF-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0c5c-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="c0c5c-110">Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c0c5c-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0c5c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0c5c-111">See also</span></span>

- [<span data-ttu-id="c0c5c-112">WPF-und Windows Forms Interoperation</span><span class="sxs-lookup"><span data-stu-id="c0c5c-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
