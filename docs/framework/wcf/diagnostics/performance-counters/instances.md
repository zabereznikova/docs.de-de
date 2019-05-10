---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651835"
---
# <a name="instances"></a><span data-ttu-id="2110b-102">Instanzen</span><span class="sxs-lookup"><span data-stu-id="2110b-102">Instances</span></span>
<span data-ttu-id="2110b-103">Indikatorname: -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="2110b-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2110b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2110b-104">Description</span></span>  
 <span data-ttu-id="2110b-105">Anzahl an Instanzkontexten, die der Dienst gerade enthält.</span><span class="sxs-lookup"><span data-stu-id="2110b-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="2110b-106">Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch.</span><span class="sxs-lookup"><span data-stu-id="2110b-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="2110b-107">Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="2110b-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="2110b-108">Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.</span><span class="sxs-lookup"><span data-stu-id="2110b-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="2110b-109">Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="2110b-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2110b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2110b-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
