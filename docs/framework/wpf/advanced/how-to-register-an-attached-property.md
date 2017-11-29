---
title: "Gewusst wie: Registrieren einer angefügten Eigenschaft"
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
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aecb5d2f35b8532ad2ae7558af1a93243b0fd6df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="ed279-102">Gewusst wie: Registrieren einer angefügten Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ed279-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="ed279-103">In diesem Beispiel wird das Registrieren einer angefügten Eigenschaft und das Bereitstellen öffentlicher Accessoren beschrieben, damit Sie die Eigenschaft jeweils in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und in Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ed279-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="ed279-104">Angefügte Eigenschaften sind ein von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiertes Syntaxkonzept.</span><span class="sxs-lookup"><span data-stu-id="ed279-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ed279-105">Die meisten angefügten Eigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Typen werden auch als Abhängigkeitseigenschaften implementiert.</span><span class="sxs-lookup"><span data-stu-id="ed279-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="ed279-106">Können Sie für ein beliebiges Abhängigkeitseigenschaften <xref:System.Windows.DependencyObject> Typen.</span><span class="sxs-lookup"><span data-stu-id="ed279-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed279-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed279-107">Example</span></span>  
 <span data-ttu-id="ed279-108">Im folgende Beispiel wird gezeigt, wie zum Registrieren einer angefügten Eigenschaft als eine Abhängigkeitseigenschaft mit dem <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ed279-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="ed279-109">Die Providerklasse hat die Möglichkeit zur Bereitstellung von Standardmetadaten für die Eigenschaft, die angewendet wird, wenn die Eigenschaft in einer anderen Klasse verwendet wird, es sei denn, diese Klasse überschreibt die Metadaten.</span><span class="sxs-lookup"><span data-stu-id="ed279-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="ed279-110">In diesem Beispiel wird der Standardwert der `IsBubbleSource`-Eigenschaft auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ed279-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="ed279-111">Die Anbieterklasse für eine angefügte Eigenschaft (auch wenn diese nicht als Abhängigkeitseigenschaft registriert ist) muss statische get- und set-Accessoren bereitstellen, die die Benennungskonvention `Set`*[NameDerAngefügtenEigenschaft]* und `Get`*[NameDerAngefügtenEigenschaft]* befolgen.</span><span class="sxs-lookup"><span data-stu-id="ed279-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="ed279-112">Diese Accessoren sind erforderlich, damit der agierende Leser von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die Eigenschaft als Attribut in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erkennen und die entsprechenden Typen auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="ed279-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="ed279-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed279-113">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="ed279-114">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="ed279-114">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="ed279-115">Benutzerdefinierte Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="ed279-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="ed279-116">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="ed279-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
