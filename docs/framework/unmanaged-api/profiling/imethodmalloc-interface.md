---
title: IMethodMalloc-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 12b97b28383eb7c39f20ee0e88f55d48e60ad956
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494098"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="d5f1b-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5f1b-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="d5f1b-103">Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5f1b-104">Die- `IMethodMalloc` Schnittstelle ist eine einfache Speicherzuweisung.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="d5f1b-105">Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5f1b-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="d5f1b-106">Methods</span></span>  
  
|<span data-ttu-id="d5f1b-107">Methode</span><span class="sxs-lookup"><span data-stu-id="d5f1b-107">Method</span></span>|<span data-ttu-id="d5f1b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5f1b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5f1b-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="d5f1b-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="d5f1b-110">Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5f1b-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d5f1b-111">Remarks</span></span>  
 <span data-ttu-id="d5f1b-112">Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="d5f1b-113">Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d5f1b-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f1b-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d5f1b-114">Requirements</span></span>  
 <span data-ttu-id="d5f1b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5f1b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5f1b-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5f1b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5f1b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5f1b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5f1b-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f1b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f1b-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d5f1b-119">See also</span></span>

- [<span data-ttu-id="d5f1b-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5f1b-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
