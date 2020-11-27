---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: f4bf639e626945c7e753ac352dfecc7a79541bfd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266076"
---
# <a name="instances"></a><span data-ttu-id="698fb-102">Instanzen</span><span class="sxs-lookup"><span data-stu-id="698fb-102">Instances</span></span>

<span data-ttu-id="698fb-103">Indikatorname: Instanzen.</span><span class="sxs-lookup"><span data-stu-id="698fb-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="698fb-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="698fb-104">Description</span></span>  

 <span data-ttu-id="698fb-105">Anzahl an Instanzkontexten, die der Dienst gerade enthält.</span><span class="sxs-lookup"><span data-stu-id="698fb-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="698fb-106">Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch.</span><span class="sxs-lookup"><span data-stu-id="698fb-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="698fb-107">Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="698fb-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="698fb-108">Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.</span><span class="sxs-lookup"><span data-stu-id="698fb-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="698fb-109">Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="698fb-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698fb-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="698fb-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
