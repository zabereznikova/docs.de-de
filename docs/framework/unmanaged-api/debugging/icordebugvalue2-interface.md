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
ms.openlocfilehash: c6f20b0f7927d79ee56b5b6962137d668dc048d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791119"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="a4a01-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4a01-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="a4a01-103">Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a4a01-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4a01-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4a01-104">Methods</span></span>  
  
|<span data-ttu-id="a4a01-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="a4a01-105">Method</span></span>|<span data-ttu-id="a4a01-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4a01-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4a01-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="a4a01-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="a4a01-108">Ruft einen Schnittstellen Zeiger auf ein `ICorDebugType` Objekt ab, das die <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4a01-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a01-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4a01-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4a01-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4a01-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4a01-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4a01-111">Requirements</span></span>  
 <span data-ttu-id="a4a01-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a01-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a01-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4a01-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4a01-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4a01-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4a01-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a01-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4a01-116">See also</span></span>

- [<span data-ttu-id="a4a01-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4a01-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="a4a01-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4a01-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
