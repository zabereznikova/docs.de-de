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
ms.openlocfilehash: f7635dc3fad9b3de30fa052c7d2e67a7e6953fb3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789041"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="781c7-102">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="781c7-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="781c7-103">Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.</span><span class="sxs-lookup"><span data-stu-id="781c7-103">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="781c7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="781c7-104">Methods</span></span>  
  
|<span data-ttu-id="781c7-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="781c7-105">Method</span></span>|<span data-ttu-id="781c7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="781c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="781c7-107">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="781c7-107">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="781c7-108">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="781c7-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="781c7-109">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="781c7-109">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="781c7-110">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="781c7-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="781c7-111">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="781c7-111">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="781c7-112">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="781c7-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="781c7-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="781c7-113">Remarks</span></span>  
 <span data-ttu-id="781c7-114">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="781c7-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="781c7-115">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="781c7-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="781c7-116">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="781c7-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="781c7-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="781c7-117">Requirements</span></span>  
 <span data-ttu-id="781c7-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="781c7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="781c7-119">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="781c7-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="781c7-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="781c7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="781c7-121">**.NET Framework Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="781c7-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781c7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="781c7-122">See also</span></span>

- [<span data-ttu-id="781c7-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="781c7-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="781c7-124">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="781c7-124">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="781c7-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="781c7-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
