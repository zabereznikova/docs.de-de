---
title: 'Vorgehensweise: Festlegen von Rändern von Elementen und Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052364"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="18c86-102">Vorgehensweise: Festlegen von Rändern von Elementen und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="18c86-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="18c86-103">In diesem Beispiel wird beschrieben, wie zum Festlegen der <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ändern Sie alle vorhandenen Eigenschaftswerte für den Rand bei Code-Behind.</span><span class="sxs-lookup"><span data-stu-id="18c86-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="18c86-104">Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ist eine Eigenschaft der <xref:System.Windows.FrameworkElement> Basis-Element und wird daher durch eine Vielzahl von Steuerelementen und anderen Elementen geerbt.</span><span class="sxs-lookup"><span data-stu-id="18c86-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="18c86-105">In diesem Beispiel hat [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], mit einem Code-Behind-Datei, die die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bezieht sich auf.</span><span class="sxs-lookup"><span data-stu-id="18c86-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="18c86-106">Das Code-Behind wird angezeigt, sowohl eine C# und eine Microsoft Visual Basic-Version.</span><span class="sxs-lookup"><span data-stu-id="18c86-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18c86-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18c86-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
