---
title: "Gewusst wie: Festlegen von R&#228;ndern von Elementen und Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Margin-Eigenschaft, Festlegen"
  - "Eigenschaften, Margin-Eigenschaft"
  - "Festlegen, Margin-Eigenschaft"
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Festlegen von R&#228;ndern von Elementen und Steuerelementen
In diesem Beispiel wird beschrieben, wie die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft festgelegt wird, indem vorhandene Eigenschaftswerte für einen Rand im Code\-Behind geändert wird.  Die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft ist eine Eigenschaft des <xref:System.Windows.FrameworkElement>\-Basiselements und wird deshalb von einer Vielzahl von Steuerelementen und anderen Elementen geerbt.  
  
 Dieses Beispiel ist in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] geschrieben und verfügt über eine Code\-Behind\-Datei, auf die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verweist.  Die Code\-Behind\-Datei wird sowohl in einer [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Version als auch in einer [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]\-Version angezeigt.  
  
## Beispiel  
 [!code-xml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]