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
ms.openlocfilehash: 8eccdba75b59df505ae72d74cfcd2bc83de2b45a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688171"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="95f23-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95f23-102">IMethodMalloc Interface</span></span>

<span data-ttu-id="95f23-103">Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.</span><span class="sxs-lookup"><span data-stu-id="95f23-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95f23-104">Die- `IMethodMalloc` Schnittstelle ist eine einfache Speicherzuweisung.</span><span class="sxs-lookup"><span data-stu-id="95f23-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="95f23-105">Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="95f23-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95f23-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="95f23-106">Methods</span></span>  
  
|<span data-ttu-id="95f23-107">Methode</span><span class="sxs-lookup"><span data-stu-id="95f23-107">Method</span></span>|<span data-ttu-id="95f23-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="95f23-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95f23-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="95f23-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="95f23-110">Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="95f23-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95f23-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95f23-111">Remarks</span></span>  

 <span data-ttu-id="95f23-112">Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat.</span><span class="sxs-lookup"><span data-stu-id="95f23-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="95f23-113">Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="95f23-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f23-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95f23-114">Requirements</span></span>  

 <span data-ttu-id="95f23-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f23-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f23-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95f23-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95f23-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f23-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f23-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f23-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f23-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95f23-119">See also</span></span>

- [<span data-ttu-id="95f23-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="95f23-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
