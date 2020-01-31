---
title: ICorDebugValue3 Interface
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791094"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="91750-102">ICorDebugValue3 Interface</span><span class="sxs-lookup"><span data-stu-id="91750-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="91750-103">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="91750-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91750-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="91750-104">Methods</span></span>  
  
|<span data-ttu-id="91750-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="91750-105">Method</span></span>|<span data-ttu-id="91750-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91750-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91750-107">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="91750-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="91750-108">Ruft die Größe dieses `ICorDebugValue3` Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="91750-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91750-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91750-109">Remarks</span></span>  
 <span data-ttu-id="91750-110">Die [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) -Methode gibt eine Objektgröße zwischen 0 und 2.147.483.647 Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="91750-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="91750-111">Im .NET Framework 4,5 kann die Größe der Arrays 2 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="91750-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="91750-112">Die `ICorDebugValue3`-Schnittstelle ermöglicht es Ihnen, die Größe dieser Arrays zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="91750-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91750-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91750-113">Requirements</span></span>  
 <span data-ttu-id="91750-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91750-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91750-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91750-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91750-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91750-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91750-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91750-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91750-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91750-118">See also</span></span>

- [<span data-ttu-id="91750-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91750-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="91750-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="91750-120">Debugging</span></span>](index.md)
