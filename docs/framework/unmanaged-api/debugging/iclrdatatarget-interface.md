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
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860565"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="233b6-102">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="233b6-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="233b6-103">Stellt Methoden für die Interaktion mit einem Ziel Element des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="233b6-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="233b6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="233b6-104">Methods</span></span>  
  
|<span data-ttu-id="233b6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-105">Method</span></span>|<span data-ttu-id="233b6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="233b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="233b6-107">GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="233b6-108">Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="233b6-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="233b6-109">GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="233b6-110">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="233b6-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="233b6-111">GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="233b6-112">Ruft einen Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="233b6-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="233b6-113">GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="233b6-114">Ruft die Größe eines Zeigers auf das aktuelle Ziel in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="233b6-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="233b6-115">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="233b6-116">Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="233b6-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="233b6-117">GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="233b6-118">Ruft einen Wert im lokalen Thread Speicher (TLS) am angegebenen Index für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="233b6-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="233b6-119">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="233b6-120">Liest Daten aus der angegebenen Adresse des virtuellen Speichers in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="233b6-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="233b6-121">Anforderungs Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="233b6-122">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="233b6-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="233b6-123">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="233b6-124">Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="233b6-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="233b6-125">SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="233b6-126">Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="233b6-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="233b6-127">WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="233b6-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="233b6-128">Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.</span><span class="sxs-lookup"><span data-stu-id="233b6-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="233b6-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="233b6-129">Remarks</span></span>  
 <span data-ttu-id="233b6-130">Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren.</span><span class="sxs-lookup"><span data-stu-id="233b6-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="233b6-131">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="233b6-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="233b6-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="233b6-132">Requirements</span></span>  
 <span data-ttu-id="233b6-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="233b6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="233b6-134">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="233b6-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="233b6-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="233b6-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="233b6-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="233b6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233b6-137">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="233b6-137">See also</span></span>

- [<span data-ttu-id="233b6-138">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="233b6-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="233b6-139">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="233b6-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
