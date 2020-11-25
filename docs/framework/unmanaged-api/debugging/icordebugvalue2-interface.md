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
ms.openlocfilehash: 7aca5fcb5a55331756b4f98c08eb46fc4db1e289
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720333"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="a072c-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a072c-102">ICorDebugValue2 Interface</span></span>

<span data-ttu-id="a072c-103">Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a072c-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a072c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a072c-104">Methods</span></span>  
  
|<span data-ttu-id="a072c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a072c-105">Method</span></span>|<span data-ttu-id="a072c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a072c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a072c-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="a072c-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="a072c-108">Ruft einen Schnittstellen Zeiger auf ein- `ICorDebugType` Objekt ab, das den <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="a072c-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a072c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a072c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a072c-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a072c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a072c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a072c-111">Requirements</span></span>  

 <span data-ttu-id="a072c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a072c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a072c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a072c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a072c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a072c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a072c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a072c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a072c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a072c-116">See also</span></span>

- [<span data-ttu-id="a072c-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a072c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="a072c-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a072c-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
