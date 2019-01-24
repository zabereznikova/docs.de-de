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
ms.openlocfilehash: 6f5c21d329ed35f82e36c2d88ac911401799e820
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596019"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="be2e8-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be2e8-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="be2e8-103">Stellt eine Methode zum Belegen von Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf.</span><span class="sxs-lookup"><span data-stu-id="be2e8-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be2e8-104">Die `IMethodMalloc` Schnittstelle ist eine einfache speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="be2e8-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="be2e8-105">Sie können Speicher zugewiesen werden, aber nicht die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="be2e8-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be2e8-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="be2e8-106">Methods</span></span>  
  
|<span data-ttu-id="be2e8-107">Methode</span><span class="sxs-lookup"><span data-stu-id="be2e8-107">Method</span></span>|<span data-ttu-id="be2e8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be2e8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be2e8-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="be2e8-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="be2e8-110">Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Text des MSIL-Funktion zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="be2e8-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be2e8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be2e8-111">Remarks</span></span>  
 <span data-ttu-id="be2e8-112">Jede Zuweisung Modul spezifisch ist, und stellt sicher, dass der Hauptteil der Funktion mit einem positiven Offset von der Basis des Moduls werden.</span><span class="sxs-lookup"><span data-stu-id="be2e8-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="be2e8-113">Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein, damit die Zuweisung zur speicherbelegung nur für einen Funktionsrumpf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="be2e8-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be2e8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be2e8-114">Requirements</span></span>  
 <span data-ttu-id="be2e8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be2e8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be2e8-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be2e8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be2e8-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be2e8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be2e8-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be2e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2e8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be2e8-119">See also</span></span>
- [<span data-ttu-id="be2e8-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="be2e8-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
