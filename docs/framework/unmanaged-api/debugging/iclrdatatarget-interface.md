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
ms.openlocfilehash: b0a5abe8877c8414443fadc00e223df240721132
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410441"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="43453-102">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43453-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="43453-103">Stellt Methoden für die Interaktion mit einem Zielelement der common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="43453-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43453-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="43453-104">Methods</span></span>  
  
|<span data-ttu-id="43453-105">Methode</span><span class="sxs-lookup"><span data-stu-id="43453-105">Method</span></span>|<span data-ttu-id="43453-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43453-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43453-107">GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="43453-108">Ruft den Bezeichner des Betriebssystems für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="43453-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="43453-109">GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="43453-110">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="43453-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="43453-111">GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="43453-112">Ruft einen Bezeichner für die Art der Anweisungssatz, der der Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="43453-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="43453-113">GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="43453-114">Ruft die Größe in Bytes, der einen Zeiger auf das aktuelle Ziel an.</span><span class="sxs-lookup"><span data-stu-id="43453-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="43453-115">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="43453-116">Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="43453-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="43453-117">GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="43453-118">Ruft einen Wert im lokalen Threadspeicher (TLS) am angegebenen Index für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="43453-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="43453-119">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="43453-120">Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="43453-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="43453-121">Request-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="43453-122">Wird von der common Language Runtime (CLR) Daten Access Services zum Anfordern eines Vorgangs aufgerufen, wie durch die Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="43453-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="43453-123">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="43453-124">Legt den aktuellen Kontext des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="43453-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="43453-125">SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="43453-126">Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="43453-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="43453-127">WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="43453-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="43453-128">Schreibt Daten aus dem angegebenen Puffer auf die angegebene virtuelle Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="43453-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43453-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43453-129">Remarks</span></span>  
 <span data-ttu-id="43453-130">Der API-Client (d. h. der Debugger) muss diese Schnittstelle für die jeweiligen Zielelement geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="43453-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="43453-131">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="43453-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43453-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43453-132">Requirements</span></span>  
 <span data-ttu-id="43453-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43453-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43453-134">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="43453-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="43453-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43453-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43453-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43453-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43453-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43453-137">See Also</span></span>  
 [<span data-ttu-id="43453-138">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43453-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="43453-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="43453-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
