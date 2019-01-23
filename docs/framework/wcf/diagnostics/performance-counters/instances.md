---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 1b2801b5df3a5d2ca6d7fd03299ecdf4b7df426a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520266"
---
# <a name="instances"></a><span data-ttu-id="8fe5d-102">Instanzen</span><span class="sxs-lookup"><span data-stu-id="8fe5d-102">Instances</span></span>
<span data-ttu-id="8fe5d-103">Indikatorname: -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8fe5d-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fe5d-104">Description</span></span>  
 <span data-ttu-id="8fe5d-105">Anzahl an Instanzkontexten, die der Dienst gerade enthält.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="8fe5d-106">Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="8fe5d-107">Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="8fe5d-108">Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="8fe5d-109">Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="8fe5d-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe5d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe5d-110">See also</span></span>
- <xref:System.ServiceModel.OperationBehaviorAttribute>
