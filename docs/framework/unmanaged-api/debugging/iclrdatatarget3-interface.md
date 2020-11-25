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
ms.openlocfilehash: 7297bfa5297878dde6867a99029ac88754a05290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723583"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="44d67-102">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44d67-102">ICLRDataTarget3 Interface</span></span>

<span data-ttu-id="44d67-103">Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.</span><span class="sxs-lookup"><span data-stu-id="44d67-103">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44d67-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="44d67-104">Methods</span></span>  
  
|<span data-ttu-id="44d67-105">Methode</span><span class="sxs-lookup"><span data-stu-id="44d67-105">Method</span></span>|<span data-ttu-id="44d67-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44d67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44d67-107">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="44d67-107">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="44d67-108">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="44d67-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="44d67-109">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="44d67-109">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="44d67-110">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="44d67-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="44d67-111">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="44d67-111">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="44d67-112">Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="44d67-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44d67-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44d67-113">Remarks</span></span>  

 <span data-ttu-id="44d67-114">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="44d67-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="44d67-115">So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="44d67-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="44d67-116">Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.</span><span class="sxs-lookup"><span data-stu-id="44d67-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d67-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="44d67-117">Requirements</span></span>  

 <span data-ttu-id="44d67-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44d67-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d67-119">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="44d67-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="44d67-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d67-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44d67-121">**.NET Framework Versionen:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44d67-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d67-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44d67-122">See also</span></span>

- [<span data-ttu-id="44d67-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44d67-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="44d67-124">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44d67-124">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="44d67-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="44d67-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
