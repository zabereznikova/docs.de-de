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
ms.openlocfilehash: dee5108439610b67c3397cebcd8ee5f84d4eacea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723635"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="40cc1-102">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40cc1-102">ICLRDataTarget2 Interface</span></span>

<span data-ttu-id="40cc1-103">Eine Unterklasse von [ICLRDataTarget](iclrdatatarget-interface.md) , die von der Ebene der Datenzugriffs Dienste zum Bearbeiten virtueller Speicherbereiche im Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40cc1-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40cc1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="40cc1-104">Methods</span></span>  
  
|<span data-ttu-id="40cc1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="40cc1-105">Method</span></span>|<span data-ttu-id="40cc1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40cc1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40cc1-107">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="40cc1-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="40cc1-108">Weist Speicher im Adressraum des Ziel Prozesses zu.</span><span class="sxs-lookup"><span data-stu-id="40cc1-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="40cc1-109">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="40cc1-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="40cc1-110">Gibt Arbeitsspeicher frei, der zuvor im Adressraum des Ziel Prozesses zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="40cc1-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40cc1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40cc1-111">Remarks</span></span>  

 <span data-ttu-id="40cc1-112">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="40cc1-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="40cc1-113">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="40cc1-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="40cc1-114">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="40cc1-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40cc1-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="40cc1-115">Requirements</span></span>  

 <span data-ttu-id="40cc1-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40cc1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40cc1-117">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="40cc1-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="40cc1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40cc1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40cc1-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40cc1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cc1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40cc1-120">See also</span></span>

- [<span data-ttu-id="40cc1-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40cc1-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="40cc1-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="40cc1-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
