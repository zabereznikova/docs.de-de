---
title: ICLRDataTarget3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: a6591f7d7b632bcdbdabb1633f7431d79da7ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111817"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="012b4-102">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="012b4-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="012b4-103">Eine Unterklasse von [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.</span><span class="sxs-lookup"><span data-stu-id="012b4-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="012b4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="012b4-104">Methods</span></span>  
  
|<span data-ttu-id="012b4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="012b4-105">Method</span></span>|<span data-ttu-id="012b4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="012b4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="012b4-107">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="012b4-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="012b4-108">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="012b4-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="012b4-109">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="012b4-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="012b4-110">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="012b4-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="012b4-111">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="012b4-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="012b4-112">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="012b4-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="012b4-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="012b4-113">Remarks</span></span>  
 <span data-ttu-id="012b4-114">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="012b4-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="012b4-115">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="012b4-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="012b4-116">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="012b4-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="012b4-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="012b4-117">Requirements</span></span>  
 <span data-ttu-id="012b4-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="012b4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="012b4-119">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="012b4-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="012b4-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="012b4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="012b4-121">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="012b4-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012b4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="012b4-122">See also</span></span>

- [<span data-ttu-id="012b4-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="012b4-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="012b4-124">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="012b4-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="012b4-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="012b4-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
