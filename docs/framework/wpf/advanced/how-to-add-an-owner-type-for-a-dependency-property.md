---
title: "Gewusst wie: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93934c8f84a7257445b530e27896342bdd73aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="e6b42-102">Gewusst wie: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft</span><span class="sxs-lookup"><span data-stu-id="e6b42-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="e6b42-103">Dieses Beispiel zeigt, wie eine Klasse als Besitzer einer Abhängigkeitseigenschaft für einen anderen Typ registriert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e6b42-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="e6b42-104">Durch diese Vorgehensweise wird die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader und Eigenschaftensystem werden sowohl die Klasse als weiteren Besitzer der Eigenschaft erkennen zu können.</span><span class="sxs-lookup"><span data-stu-id="e6b42-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="e6b42-105">Durch das optional als Besitzer hinzufügen, kann die hinzufügenden Klasse um typspezifische Metadaten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e6b42-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="e6b42-106">Im folgenden Beispiel `StateProperty` eine Eigenschaft wird registriert werden, indem die `MyStateControl` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e6b42-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="e6b42-107">Die Klasse `UnrelatedStateControl` fügt sich selbst als Besitzer der `StateProperty` mithilfe der <xref:System.Windows.DependencyProperty.AddOwner%2A> Methode unter Verwendung speziell die Signatur, die neue Metadaten für die Abhängigkeitseigenschaft ermöglicht, wie sie auf der hinzufügen-Typ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6b42-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="e6b42-108">Beachten Sie, die Sie bereitstellen sollten [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Accessoren für die Eigenschaft, die ähnlich wie das Beispiel in der [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) , sowie die Bezeichner der Abhängigkeitseigenschaft für die Klasse, die hinzugefügt wird, erneut verfügbar machen als Besitzer.</span><span class="sxs-lookup"><span data-stu-id="e6b42-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="e6b42-109">Ohne Wrapper die Abhängigkeitseigenschaft funktioniert trotzdem aus der Perspektive des programmgesteuerten Zugriffs mit <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6b42-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="e6b42-110">In der Regel parallel dieses Eigenschaftensystem Verhalten mit möchten jedoch die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaftenwrapper.</span><span class="sxs-lookup"><span data-stu-id="e6b42-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="e6b42-111">Der Wrapper erleichtern die Abhängigkeitseigenschaft programmgesteuert festgelegt und können sie zum Festlegen der Eigenschaften als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute.</span><span class="sxs-lookup"><span data-stu-id="e6b42-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="e6b42-112">Um herauszufinden, wie die standardmäßigen Metadaten überschrieben, finden Sie unter [Überschreiben von Metadaten für eine Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span><span class="sxs-lookup"><span data-stu-id="e6b42-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6b42-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6b42-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="e6b42-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6b42-114">See Also</span></span>  
 [<span data-ttu-id="e6b42-115">Benutzerdefinierte Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="e6b42-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="e6b42-116">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="e6b42-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
