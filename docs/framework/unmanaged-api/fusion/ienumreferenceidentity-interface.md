---
title: IEnumReferenceIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="a5d74-102">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5d74-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="a5d74-103">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5d74-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5d74-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a5d74-104">Methods</span></span>  
  
|<span data-ttu-id="a5d74-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a5d74-105">Method</span></span>|<span data-ttu-id="a5d74-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5d74-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="a5d74-107">Ruft einen Schnittstellenzeiger auf eine neue `IEnumReferenceIdentity` , enthält das dieselben Member wie dies `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a5d74-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="a5d74-108">Ruft die angegebene Anzahl von `IReferenceIdentity` Objekte, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="a5d74-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="a5d74-109">Verschiebt den Anweisungszeiger an den Anfang `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a5d74-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="a5d74-110">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="a5d74-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5d74-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5d74-111">Requirements</span></span>  
 <span data-ttu-id="a5d74-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5d74-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d74-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="a5d74-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a5d74-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d74-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5d74-115">See Also</span></span>  
 [<span data-ttu-id="a5d74-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a5d74-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="a5d74-117">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5d74-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
