---
title: ICLRDataTarget2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697939"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="1dcc5-102">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1dcc5-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="1dcc5-103">Eine Unterklasse von [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , die von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1dcc5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1dcc5-104">Methods</span></span>  
  
|<span data-ttu-id="1dcc5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1dcc5-105">Method</span></span>|<span data-ttu-id="1dcc5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dcc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1dcc5-107">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="1dcc5-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="1dcc5-108">Belegt Speicher im Adressraum des Zielprozesses.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="1dcc5-109">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="1dcc5-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="1dcc5-110">Gibt den Arbeitsspeicher, der zuvor im Adressbereich des Zielprozesses belegt wurde frei.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dcc5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1dcc5-111">Remarks</span></span>  
 <span data-ttu-id="1dcc5-112">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="1dcc5-113">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="1dcc5-114">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="1dcc5-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dcc5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1dcc5-115">Requirements</span></span>  
 <span data-ttu-id="1dcc5-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dcc5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dcc5-117">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1dcc5-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1dcc5-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dcc5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dcc5-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dcc5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dcc5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dcc5-120">See also</span></span>

- [<span data-ttu-id="1dcc5-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1dcc5-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="1dcc5-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1dcc5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
