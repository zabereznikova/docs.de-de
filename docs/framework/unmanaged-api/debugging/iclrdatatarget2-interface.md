---
title: ICLRDataTarget2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2
helpviewer_keywords: ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8d8dc7aad35e38b2f9d3b5fb48dacbe1d22bd34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="780c7-102">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="780c7-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="780c7-103">Eine Unterklasse von [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , das von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="780c7-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="780c7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="780c7-104">Methods</span></span>  
  
|<span data-ttu-id="780c7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="780c7-105">Method</span></span>|<span data-ttu-id="780c7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="780c7-107">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="780c7-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="780c7-108">Belegt Speicher im Adressbereich des Zielprozesses.</span><span class="sxs-lookup"><span data-stu-id="780c7-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="780c7-109">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="780c7-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="780c7-110">Gibt, die zuvor im Adressbereich des Zielprozesses reservierten Arbeitsspeicher frei.</span><span class="sxs-lookup"><span data-stu-id="780c7-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="780c7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="780c7-111">Remarks</span></span>  
 <span data-ttu-id="780c7-112">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="780c7-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="780c7-113">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="780c7-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="780c7-114">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="780c7-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780c7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="780c7-115">Requirements</span></span>  
 <span data-ttu-id="780c7-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="780c7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780c7-117">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="780c7-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="780c7-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="780c7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="780c7-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780c7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780c7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="780c7-120">See Also</span></span>  
 [<span data-ttu-id="780c7-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="780c7-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="780c7-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="780c7-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
