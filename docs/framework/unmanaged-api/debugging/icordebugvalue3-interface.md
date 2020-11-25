---
title: ICorDebugValue3-Schnittstelle
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
ms.openlocfilehash: 419efc7f21f4ac2e68657b2a4d69a8690a2938d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722309"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="41753-102">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41753-102">ICorDebugValue3 Interface</span></span>

<span data-ttu-id="41753-103">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="41753-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41753-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="41753-104">Methods</span></span>  
  
|<span data-ttu-id="41753-105">Methode</span><span class="sxs-lookup"><span data-stu-id="41753-105">Method</span></span>|<span data-ttu-id="41753-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41753-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41753-107">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="41753-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="41753-108">Ruft die Größe des-Objekts in Bytes ab `ICorDebugValue3` .</span><span class="sxs-lookup"><span data-stu-id="41753-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41753-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41753-109">Remarks</span></span>  

 <span data-ttu-id="41753-110">Die [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) -Methode gibt eine Objektgröße zwischen 0 und 2.147.483.647 Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="41753-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="41753-111">Im .NET Framework 4,5 kann die Größe der Arrays 2 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="41753-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="41753-112">Die- `ICorDebugValue3` Schnittstelle ermöglicht es Ihnen, die Größe dieser Arrays zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="41753-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41753-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41753-113">Requirements</span></span>  

 <span data-ttu-id="41753-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41753-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41753-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41753-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41753-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41753-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41753-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41753-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41753-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41753-118">See also</span></span>

- [<span data-ttu-id="41753-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41753-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="41753-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="41753-120">Debugging</span></span>](index.md)
