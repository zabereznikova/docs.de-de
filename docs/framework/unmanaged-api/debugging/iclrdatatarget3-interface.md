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
ms.openlocfilehash: af944a9c2bb04f37b06f27cfbe38e23c9613d768
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860414"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="bc858-102">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc858-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="bc858-103">Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.</span><span class="sxs-lookup"><span data-stu-id="bc858-103">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc858-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc858-104">Methods</span></span>  
  
|<span data-ttu-id="bc858-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bc858-105">Method</span></span>|<span data-ttu-id="bc858-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc858-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc858-107">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="bc858-107">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="bc858-108">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bc858-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="bc858-109">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="bc858-109">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="bc858-110">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bc858-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="bc858-111">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="bc858-111">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="bc858-112">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="bc858-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc858-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc858-113">Remarks</span></span>  
 <span data-ttu-id="bc858-114">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="bc858-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="bc858-115">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="bc858-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="bc858-116">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="bc858-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc858-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc858-117">Requirements</span></span>  
 <span data-ttu-id="bc858-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc858-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc858-119">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="bc858-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bc858-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc858-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc858-121">**.NET Framework Versionen:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bc858-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc858-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bc858-122">See also</span></span>

- [<span data-ttu-id="bc858-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc858-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="bc858-124">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc858-124">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="bc858-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc858-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
