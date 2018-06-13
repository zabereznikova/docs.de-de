---
title: 'Gewusst wie: Festlegen von Rändern von Elementen und Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 41a0f1d025061cc7c1472a831fbbd5ed2f01b043
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543649"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="09718-102">Gewusst wie: Festlegen von Rändern von Elementen und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="09718-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="09718-103">In diesem Beispiel wird beschrieben, wie zum Festlegen der <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft durch einen beliebigen vorhandenen Eigenschaftswert für einen Rand im Code-Behind ändern.</span><span class="sxs-lookup"><span data-stu-id="09718-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="09718-104">Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ist eine Eigenschaft der <xref:System.Windows.FrameworkElement> Element basieren, und wird daher von einer Vielzahl von Steuerelementen und anderen Elementen geerbt.</span><span class="sxs-lookup"><span data-stu-id="09718-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="09718-105">In diesem Beispiel wird geschrieben, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], mit Code-Behind-Datei mit der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bezieht sich auf.</span><span class="sxs-lookup"><span data-stu-id="09718-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="09718-106">Das Code-Behind-Modell wird in einer C#- und Microsoft Visual Basic-Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="09718-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09718-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09718-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
