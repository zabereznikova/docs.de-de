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
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113494"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="f9a0b-102">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9a0b-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="f9a0b-103">Stellt Methoden für die Interaktion mit einem Ziel Element des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9a0b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f9a0b-104">Methods</span></span>  
  
|<span data-ttu-id="f9a0b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-105">Method</span></span>|<span data-ttu-id="f9a0b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9a0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9a0b-107">GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="f9a0b-108">Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="f9a0b-109">GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="f9a0b-110">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="f9a0b-111">GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="f9a0b-112">Ruft einen Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="f9a0b-113">GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="f9a0b-114">Ruft die Größe eines Zeigers auf das aktuelle Ziel in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="f9a0b-115">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="f9a0b-116">Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="f9a0b-117">GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="f9a0b-118">Ruft einen Wert im lokalen Thread Speicher (TLS) am angegebenen Index für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="f9a0b-119">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="f9a0b-120">Liest Daten aus der angegebenen Adresse des virtuellen Speichers in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="f9a0b-121">Request-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="f9a0b-122">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="f9a0b-123">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="f9a0b-124">Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="f9a0b-125">SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="f9a0b-126">Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="f9a0b-127">WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a0b-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="f9a0b-128">Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9a0b-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9a0b-129">Remarks</span></span>  
 <span data-ttu-id="f9a0b-130">Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="f9a0b-131">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="f9a0b-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a0b-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9a0b-132">Requirements</span></span>  
 <span data-ttu-id="f9a0b-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a0b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a0b-134">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="f9a0b-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f9a0b-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9a0b-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9a0b-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a0b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a0b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9a0b-137">See also</span></span>

- [<span data-ttu-id="f9a0b-138">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9a0b-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="f9a0b-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f9a0b-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
