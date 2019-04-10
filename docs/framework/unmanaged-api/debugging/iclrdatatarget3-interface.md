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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df113a2839b0f2651e15f4029d86cc5efc171c63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111812"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="39496-102">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39496-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="39496-103">Eine Unterklasse von [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , Zugriff auf Informationen über die Ausnahme bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="39496-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39496-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="39496-104">Methods</span></span>  
  
|<span data-ttu-id="39496-105">Methode</span><span class="sxs-lookup"><span data-stu-id="39496-105">Method</span></span>|<span data-ttu-id="39496-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39496-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39496-107">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="39496-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="39496-108">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="39496-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="39496-109">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="39496-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="39496-110">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="39496-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="39496-111">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="39496-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="39496-112">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="39496-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39496-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39496-113">Remarks</span></span>  
 <span data-ttu-id="39496-114">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="39496-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="39496-115">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="39496-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="39496-116">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="39496-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39496-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39496-117">Requirements</span></span>  
 <span data-ttu-id="39496-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39496-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39496-119">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="39496-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="39496-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39496-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="39496-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="39496-121">.NET Framework Versions:</span></span>** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39496-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39496-122">See also</span></span>

- [<span data-ttu-id="39496-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39496-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="39496-124">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39496-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="39496-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="39496-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
