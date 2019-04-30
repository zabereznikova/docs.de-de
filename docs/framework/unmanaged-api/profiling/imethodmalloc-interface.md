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
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969805"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="7212f-102">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7212f-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="7212f-103">Stellt eine Methode zum Belegen von Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf.</span><span class="sxs-lookup"><span data-stu-id="7212f-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7212f-104">Die `IMethodMalloc` Schnittstelle ist eine einfache speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="7212f-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="7212f-105">Sie können Speicher zugewiesen werden, aber nicht die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="7212f-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7212f-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="7212f-106">Methods</span></span>  
  
|<span data-ttu-id="7212f-107">Methode</span><span class="sxs-lookup"><span data-stu-id="7212f-107">Method</span></span>|<span data-ttu-id="7212f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7212f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7212f-109">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="7212f-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="7212f-110">Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Text des MSIL-Funktion zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="7212f-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7212f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7212f-111">Remarks</span></span>  
 <span data-ttu-id="7212f-112">Jede Zuweisung Modul spezifisch ist, und stellt sicher, dass der Hauptteil der Funktion mit einem positiven Offset von der Basis des Moduls werden.</span><span class="sxs-lookup"><span data-stu-id="7212f-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="7212f-113">Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein, damit die Zuweisung zur speicherbelegung nur für einen Funktionsrumpf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7212f-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7212f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7212f-114">Requirements</span></span>  
 <span data-ttu-id="7212f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7212f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7212f-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7212f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7212f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7212f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7212f-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7212f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7212f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7212f-119">See also</span></span>

- [<span data-ttu-id="7212f-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7212f-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
