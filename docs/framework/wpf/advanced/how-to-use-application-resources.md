---
title: 'Gewusst wie: Verwenden von Anwendungsressourcen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bac1fa1576e684a4b10f00310c08e4e7101a5df0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="d4e49-102">Gewusst wie: Verwenden von Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="d4e49-102">How to: Use Application Resources</span></span>
<span data-ttu-id="d4e49-103">In diesem Beispiel wird veranschaulicht, wie Sie Anwendungsressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4e49-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e49-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4e49-104">Example</span></span>  
 <span data-ttu-id="d4e49-105">Das folgende Beispiel zeigt eine Anwendungsdefinitionsdatei.</span><span class="sxs-lookup"><span data-stu-id="d4e49-105">The following example shows an application definition file.</span></span> <span data-ttu-id="d4e49-106">Die Anwendungsdefinitionsdatei definiert einen Ressourcenabschnitt (einen Wert für die <xref:System.Windows.Application.Resources%2A> Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="d4e49-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="d4e49-107">Auf Ressourcen, die auf Anwendungsebene definiert sind, kann von allen anderen Seiten zugegriffen werden, die Teil der Anwendung sind.</span><span class="sxs-lookup"><span data-stu-id="d4e49-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="d4e49-108">In diesem Fall ist die Ressource ein deklarierter Stil.</span><span class="sxs-lookup"><span data-stu-id="d4e49-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="d4e49-109">Da ein vollständiger Stil, die eine Steuerelementvorlage enthält lange sein kann, wird in diesem Beispiel wird die Steuerelementvorlage, die im definiert ist die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Setter für eine Eigenschaft des Formats.</span><span class="sxs-lookup"><span data-stu-id="d4e49-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="d4e49-110">Das folgende Beispiel zeigt eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite, die die Ressource auf Anwendungsebene verweist, die im vorherige Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="d4e49-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="d4e49-111">Die Ressource mit verwiesen wird eine [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , die die eindeutigen Ressourcenschlüssel für die angeforderte Ressource angibt.</span><span class="sxs-lookup"><span data-stu-id="d4e49-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="d4e49-112">Es wird keine Ressource mit dem Schlüssel „GelButton“ auf der aktuellen Seite gefunden, deshalb macht der Ressourcensuchbereich für die angeforderte Ressource über die aktuelle Seite hinaus weiter und in den definierten Ressourcen auf Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="d4e49-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e49-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4e49-113">See Also</span></span>  
 [<span data-ttu-id="d4e49-114">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d4e49-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="d4e49-115">Übersicht über die Anwendungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d4e49-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [<span data-ttu-id="d4e49-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d4e49-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
