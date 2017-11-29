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
ms.openlocfilehash: 322ac3e5ebfe2d820a4711d877396b9a1a2759a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="543c1-102">Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource</span><span class="sxs-lookup"><span data-stu-id="543c1-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="543c1-103">In diesem Beispiel wird gezeigt, wie eine Ressource definiert, und verweisen sie mit einem Attribut in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="543c1-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="543c1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="543c1-104">Example</span></span>  
 <span data-ttu-id="543c1-105">Im folgende Beispiel werden zwei Typen von Ressourcen definiert: eine <xref:System.Windows.Media.SolidColorBrush> Ressource und mehrere <xref:System.Windows.Style> Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="543c1-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="543c1-106">Die <xref:System.Windows.Media.SolidColorBrush> Ressource `MyBrush` wird verwendet, um dem Wert verschiedener Eigenschaften angeben, die jeweils eine <xref:System.Windows.Media.Brush> Typwert.</span><span class="sxs-lookup"><span data-stu-id="543c1-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="543c1-107">Die <xref:System.Windows.Style> Ressourcen `PageBackground`, `TitleText` und `Label` jeweils einen bestimmten Steuerelementtyp abzielen.</span><span class="sxs-lookup"><span data-stu-id="543c1-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="543c1-108">Die Stile legen Sie eine Vielzahl von verschiedenen Eigenschaften für die entsprechenden Steuerelemente, wenn die Stilressource Ressourcenschlüssel verweist und zum Festlegen dient der <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft mehrerer bestimmtes Steuerelement-Elemente, die in definierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="543c1-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="543c1-109">Beachten Sie, dass einer der Eigenschaften in den Settern des der `Label` Stil verweist außerdem auf die `MyBrush` Ressource, die zuvor definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="543c1-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="543c1-110">Dies ist ein gängiges Verfahren, aber es ist wichtig zu beachten, dass die Ressourcen werden analysiert und eingegeben werden, in einem Ressourcenwörterbuch, in der Reihenfolge, die ihm zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="543c1-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="543c1-111">Ressourcen sind auch angefordert, durch die Reihenfolge im Wörterbuch gefunden wird, wenn Sie verwenden die [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) aus einer anderen Ressource verweisen.</span><span class="sxs-lookup"><span data-stu-id="543c1-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="543c1-112">Stellen Sie sicher, dass alle Ressourcen, die Sie verweisen, weiter oben definiert ist, in der Auflistung Ressourcen als der, in dem die Ressource dann angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="543c1-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="543c1-113">Wenn erforderlich, die strenge Erstellungsreihenfolge sortiert der Ressource Erstellungsreihenfolge mit können Sie umgehen eine [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) auf die Ressource zur Laufzeit stattdessen verweisen, aber Sie sollten sich bewusst sein, die diese DynamicResource Technik wurde die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="543c1-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="543c1-114">Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="543c1-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="543c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="543c1-115">See Also</span></span>  
 [<span data-ttu-id="543c1-116">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="543c1-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="543c1-117">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="543c1-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
