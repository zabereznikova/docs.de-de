---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73ed25406aa398aa35c275b20da1deee48b119ab
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="3d779-102">Gewusst wie: Erstellen einer einfachen Bindung</span><span class="sxs-lookup"><span data-stu-id="3d779-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="3d779-103">Dieses Beispiel veranschaulicht das Erstellen eines einfachen <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="3d779-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d779-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d779-104">Example</span></span>  
 <span data-ttu-id="3d779-105">In diesem Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="3d779-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="3d779-106">Die `Person` Objekt ist im Namespace namens definiert `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="3d779-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="3d779-107">Das folgende Beispiel instanziiert die `Person` -Objekt mit einer `PersonName` Eigenschaftswert `Joe`.</span><span class="sxs-lookup"><span data-stu-id="3d779-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="3d779-108">Dies erfolgt in der `Resources` Abschnitt zugewiesen, und wählen Sie eine `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="3d779-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml)]  
  
 <span data-ttu-id="3d779-109">Zum Binden an die `PersonName` Eigenschaft würden Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="3d779-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="3d779-110">Daher die <xref:System.Windows.Controls.TextBlock> wird mit dem Wert "Joe" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d779-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d779-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d779-111">See Also</span></span>  
 [<span data-ttu-id="3d779-112">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="3d779-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3d779-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="3d779-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
