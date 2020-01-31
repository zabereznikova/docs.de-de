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
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793715"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="7027d-102">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7027d-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="7027d-103">Stellt Methoden für die Interaktion mit einem Ziel Element des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="7027d-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7027d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7027d-104">Methods</span></span>  
  
|<span data-ttu-id="7027d-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-105">Method</span></span>|<span data-ttu-id="7027d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7027d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7027d-107">GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="7027d-108">Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="7027d-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="7027d-109">GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="7027d-110">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="7027d-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="7027d-111">GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="7027d-112">Ruft einen Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7027d-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="7027d-113">GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="7027d-114">Ruft die Größe eines Zeigers auf das aktuelle Ziel in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="7027d-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="7027d-115">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="7027d-116">Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="7027d-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="7027d-117">GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="7027d-118">Ruft einen Wert im lokalen Thread Speicher (TLS) am angegebenen Index für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="7027d-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="7027d-119">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="7027d-120">Liest Daten aus der angegebenen Adresse des virtuellen Speichers in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="7027d-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="7027d-121">Request-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="7027d-122">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="7027d-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="7027d-123">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="7027d-124">Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="7027d-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="7027d-125">SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="7027d-126">Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="7027d-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="7027d-127">WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="7027d-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="7027d-128">Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.</span><span class="sxs-lookup"><span data-stu-id="7027d-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7027d-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7027d-129">Remarks</span></span>  
 <span data-ttu-id="7027d-130">Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren.</span><span class="sxs-lookup"><span data-stu-id="7027d-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="7027d-131">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="7027d-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7027d-132">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7027d-132">Requirements</span></span>  
 <span data-ttu-id="7027d-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7027d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7027d-134">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="7027d-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7027d-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7027d-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7027d-136">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7027d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7027d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7027d-137">See also</span></span>

- [<span data-ttu-id="7027d-138">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7027d-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="7027d-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7027d-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
