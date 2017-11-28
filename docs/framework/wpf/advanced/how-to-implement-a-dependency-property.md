---
title: "Gewusst wie: Implementieren einer Abhängigkeitseigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bc4dee8f0b2eef76e5769ae7da3a13edf7c3300
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="522fc-102">Gewusst wie: Implementieren einer Abhängigkeitseigenschaft</span><span class="sxs-lookup"><span data-stu-id="522fc-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="522fc-103">Dieses Beispiel zeigt, wie Sie eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Eigenschaft mit einer <xref:System.Windows.DependencyProperty> Feld, definieren daher eine Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="522fc-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="522fc-104">Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.</span><span class="sxs-lookup"><span data-stu-id="522fc-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="522fc-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="522fc-105">Example</span></span>  
 <span data-ttu-id="522fc-106">Das folgende Beispiel registriert eine Abhängigkeitseigenschaft zunächst durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="522fc-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="522fc-107">Der Name des Bezeichnerfelds, mit denen Sie den Namen zu speichern und Merkmale der Abhängigkeitseigenschaft muss die <xref:System.Windows.DependencyProperty.Name%2A> gewählten für die Abhängigkeitseigenschaft als Teil der <xref:System.Windows.DependencyProperty.Register%2A> Aufruf, der von der literalen Zeichenfolge angefügt `Property`.</span><span class="sxs-lookup"><span data-stu-id="522fc-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="522fc-108">Z. B., wenn Sie eine Abhängigkeitseigenschaft mit dem Registrieren einer <xref:System.Windows.DependencyProperty.Name%2A> von `Location`, muss den Namen das ID-Feld, die Sie für die Abhängigkeitseigenschaft definieren `LocationProperty`.</span><span class="sxs-lookup"><span data-stu-id="522fc-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="522fc-109">In diesem Beispiel den Namen der Abhängigkeitseigenschaft und die zugehörige [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Accessor `State`; der Feld-ID ist `StateProperty`; der Typ der Eigenschaft ist <xref:System.Boolean>; und der Typ, der die Abhängigkeitseigenschaft registriert wird `MyStateControl`.</span><span class="sxs-lookup"><span data-stu-id="522fc-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="522fc-110">Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.</span><span class="sxs-lookup"><span data-stu-id="522fc-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="522fc-111">Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="522fc-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="522fc-112">Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.</span><span class="sxs-lookup"><span data-stu-id="522fc-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="522fc-113">Weitere Informationen dazu, wie und warum eine Abhängigkeitseigenschaft implementiert wird, anstatt eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaft nur mit einem privaten Feld zu sichern, finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="522fc-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522fc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="522fc-114">See Also</span></span>  
 [<span data-ttu-id="522fc-115">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="522fc-115">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="522fc-116">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="522fc-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
