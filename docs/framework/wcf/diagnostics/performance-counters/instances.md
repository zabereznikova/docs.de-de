---
title: Instanzen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23182f18f28cfb843c1c3a70996590a92d9cdea8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="instances"></a><span data-ttu-id="87e87-102">Instanzen</span><span class="sxs-lookup"><span data-stu-id="87e87-102">Instances</span></span>
<span data-ttu-id="87e87-103">Indikatorname: Instanzen.</span><span class="sxs-lookup"><span data-stu-id="87e87-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="87e87-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e87-104">Description</span></span>  
 <span data-ttu-id="87e87-105">Anzahl an Instanzkontexten, die der Dienst gerade enthält.</span><span class="sxs-lookup"><span data-stu-id="87e87-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="87e87-106">Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch.</span><span class="sxs-lookup"><span data-stu-id="87e87-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="87e87-107">Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="87e87-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="87e87-108">Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.</span><span class="sxs-lookup"><span data-stu-id="87e87-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="87e87-109">Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="87e87-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e87-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87e87-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
