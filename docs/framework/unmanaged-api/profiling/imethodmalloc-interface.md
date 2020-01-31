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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860968"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="22d7d-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22d7d-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="22d7d-103">Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.</span><span class="sxs-lookup"><span data-stu-id="22d7d-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d7d-104">Die `IMethodMalloc`-Schnittstelle ist eine einfache Speicherzuweisung.</span><span class="sxs-lookup"><span data-stu-id="22d7d-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="22d7d-105">Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="22d7d-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22d7d-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="22d7d-106">Methods</span></span>  
  
|<span data-ttu-id="22d7d-107">-Methode</span><span class="sxs-lookup"><span data-stu-id="22d7d-107">Method</span></span>|<span data-ttu-id="22d7d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22d7d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22d7d-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="22d7d-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="22d7d-110">Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="22d7d-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d7d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22d7d-111">Remarks</span></span>  
 <span data-ttu-id="22d7d-112">Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat.</span><span class="sxs-lookup"><span data-stu-id="22d7d-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="22d7d-113">Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="22d7d-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d7d-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22d7d-114">Requirements</span></span>  
 <span data-ttu-id="22d7d-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22d7d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d7d-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22d7d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22d7d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22d7d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22d7d-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d7d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d7d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22d7d-119">See also</span></span>

- [<span data-ttu-id="22d7d-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="22d7d-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
