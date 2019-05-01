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
# <a name="how-to-set-margins-of-elements-and-controls"></a>Vorgehensweise: Festlegen von Rändern von Elementen und Steuerelementen
In diesem Beispiel wird beschrieben, wie zum Festlegen der <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ändern Sie alle vorhandenen Eigenschaftswerte für den Rand bei Code-Behind. Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ist eine Eigenschaft der <xref:System.Windows.FrameworkElement> Basis-Element und wird daher durch eine Vielzahl von Steuerelementen und anderen Elementen geerbt.  
  
 In diesem Beispiel hat [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], mit einem Code-Behind-Datei, die die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bezieht sich auf. Das Code-Behind wird angezeigt, sowohl eine C# und eine Microsoft Visual Basic-Version.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
