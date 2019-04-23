---
title: ICLRDataTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100248"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="be551-102">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be551-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="be551-103">Stellt Methoden für die Interaktion mit der common Language Runtime (CLR) ein Target-Element.</span><span class="sxs-lookup"><span data-stu-id="be551-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be551-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="be551-104">Methods</span></span>  
  
|<span data-ttu-id="be551-105">Methode</span><span class="sxs-lookup"><span data-stu-id="be551-105">Method</span></span>|<span data-ttu-id="be551-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be551-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be551-107">GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="be551-108">Ruft den Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="be551-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="be551-109">GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="be551-110">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="be551-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="be551-111">GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="be551-112">Ruft einen Bezeichner für die Art der Anweisungssatz, der der Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="be551-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="be551-113">GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="be551-114">Ruft die Größe in Bytes, der einen Zeiger auf das aktuelle Ziel.</span><span class="sxs-lookup"><span data-stu-id="be551-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="be551-115">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="be551-116">Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="be551-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="be551-117">GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="be551-118">Ruft einen Wert im lokalen Threadspeicher (TLS) am angegebenen Index für den angegebenen Thread an.</span><span class="sxs-lookup"><span data-stu-id="be551-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="be551-119">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="be551-120">Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="be551-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="be551-121">Request-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="be551-122">Aufgerufen von der common Language Runtime (CLR) Datenzugriffsdiensten der zum Anfordern eines Vorgangs, wie durch die Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="be551-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="be551-123">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="be551-124">Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest.</span><span class="sxs-lookup"><span data-stu-id="be551-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="be551-125">SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="be551-126">Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="be551-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="be551-127">WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="be551-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="be551-128">Schreibt Daten aus dem angegebenen Puffer an die Adresse des angegebenen virtuellen Speicher an.</span><span class="sxs-lookup"><span data-stu-id="be551-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be551-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be551-129">Remarks</span></span>  
 <span data-ttu-id="be551-130">Der API-Client (d. h. der Debugger), muss diese Schnittstelle für das betreffende Zielframework-Element entsprechend implementieren.</span><span class="sxs-lookup"><span data-stu-id="be551-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="be551-131">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="be551-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be551-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be551-132">Requirements</span></span>  
 <span data-ttu-id="be551-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be551-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be551-134">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="be551-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="be551-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be551-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be551-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be551-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be551-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be551-137">See also</span></span>

- [<span data-ttu-id="be551-138">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be551-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="be551-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="be551-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
