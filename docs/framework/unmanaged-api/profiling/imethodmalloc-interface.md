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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935647"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="a4d00-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4d00-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="a4d00-103">Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.</span><span class="sxs-lookup"><span data-stu-id="a4d00-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4d00-104">Die `IMethodMalloc` -Schnittstelle ist eine einfache Speicherzuweisung.</span><span class="sxs-lookup"><span data-stu-id="a4d00-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="a4d00-105">Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="a4d00-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4d00-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4d00-106">Methods</span></span>  
  
|<span data-ttu-id="a4d00-107">Methode</span><span class="sxs-lookup"><span data-stu-id="a4d00-107">Method</span></span>|<span data-ttu-id="a4d00-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4d00-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4d00-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a4d00-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="a4d00-110">Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a4d00-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4d00-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4d00-111">Remarks</span></span>  
 <span data-ttu-id="a4d00-112">Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat.</span><span class="sxs-lookup"><span data-stu-id="a4d00-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="a4d00-113">Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a4d00-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d00-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4d00-114">Requirements</span></span>  
 <span data-ttu-id="a4d00-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d00-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d00-116">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="a4d00-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4d00-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4d00-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4d00-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d00-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d00-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4d00-119">See also</span></span>

- [<span data-ttu-id="a4d00-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4d00-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
