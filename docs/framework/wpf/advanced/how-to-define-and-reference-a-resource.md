---
title: 'Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a>Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource
In diesem Beispiel wird gezeigt, wie eine Ressource definiert, und verweisen sie mit einem Attribut in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden zwei Typen von Ressourcen definiert: eine <xref:System.Windows.Media.SolidColorBrush> Ressource und mehrere <xref:System.Windows.Style> Ressourcen. Die <xref:System.Windows.Media.SolidColorBrush> Ressource `MyBrush` wird verwendet, um dem Wert verschiedener Eigenschaften angeben, die jeweils eine <xref:System.Windows.Media.Brush> Typwert. Die <xref:System.Windows.Style> Ressourcen `PageBackground`, `TitleText` und `Label` jeweils einen bestimmten Steuerelementtyp abzielen. Die Stile legen Sie eine Vielzahl von verschiedenen Eigenschaften für die entsprechenden Steuerelemente, wenn die Stilressource Ressourcenschlüssel verweist und zum Festlegen dient der <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft mehrerer bestimmtes Steuerelement-Elemente, die in definierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Beachten Sie, dass einer der Eigenschaften in den Settern des der `Label` Stil verweist außerdem auf die `MyBrush` Ressource, die zuvor definiert wurde. Dies ist ein gängiges Verfahren, aber es ist wichtig zu beachten, dass die Ressourcen werden analysiert und eingegeben werden, in einem Ressourcenwörterbuch, in der Reihenfolge, die ihm zugewiesen sind. Ressourcen sind auch angefordert, durch die Reihenfolge im Wörterbuch gefunden wird, wenn Sie verwenden die [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) aus einer anderen Ressource verweisen. Stellen Sie sicher, dass alle Ressourcen, die Sie verweisen, weiter oben definiert ist, in der Auflistung Ressourcen als der, in dem die Ressource dann angefordert wird. Wenn erforderlich, die strenge Erstellungsreihenfolge sortiert der Ressource Erstellungsreihenfolge mit können Sie umgehen eine [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) auf die Ressource zur Laufzeit stattdessen verweisen, aber Sie sollten sich bewusst sein, die diese DynamicResource Technik wurde die Leistung beeinträchtigen. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
