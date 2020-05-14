---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: d036ddf353aa3a622ade05e1e2daa7f170d28f63
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396774"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="e1ce8-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1ce8-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="e1ce8-103">Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e1ce8-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1ce8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e1ce8-104">Methods</span></span>  
  
|<span data-ttu-id="e1ce8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e1ce8-105">Method</span></span>|<span data-ttu-id="e1ce8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ce8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1ce8-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="e1ce8-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="e1ce8-108">Ruft einen Schnittstellen Zeiger auf ein- `ICorDebugType` Objekt ab, das den <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="e1ce8-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1ce8-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1ce8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1ce8-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e1ce8-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ce8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1ce8-111">Requirements</span></span>  
 <span data-ttu-id="e1ce8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1ce8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ce8-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1ce8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1ce8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1ce8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1ce8-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ce8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ce8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1ce8-116">See also</span></span>

- [<span data-ttu-id="e1ce8-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1ce8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="e1ce8-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1ce8-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
