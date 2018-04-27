---
title: 'Gewusst wie: Festlegen von Rändern von Elementen und Steuerelementen'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f32107074239e9713feaa9e0b9b7e1f89869d111
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>Gewusst wie: Festlegen von Rändern von Elementen und Steuerelementen
In diesem Beispiel wird beschrieben, wie zum Festlegen der <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft durch einen beliebigen vorhandenen Eigenschaftswert für einen Rand im Code-Behind ändern. Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ist eine Eigenschaft der <xref:System.Windows.FrameworkElement> Element basieren, und wird daher von einer Vielzahl von Steuerelementen und anderen Elementen geerbt.  
  
 In diesem Beispiel wird geschrieben, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], mit Code-Behind-Datei mit der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bezieht sich auf. Das Code-Behind-Modell wird in einer C#- und Microsoft Visual Basic-Version angezeigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
