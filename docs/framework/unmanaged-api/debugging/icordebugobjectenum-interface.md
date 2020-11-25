---
title: ICorDebugObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 9400c4fa3ddcefef923d7bcfaae80e2cef62dc7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695464"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="90cc7-102">ICorDebugObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90cc7-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="90cc7-103">Implementiert ICorDebugEnum-Methoden und listet Arrays von Objekten durch ihre relativen virtuellen Adressen (RVAs) auf.</span><span class="sxs-lookup"><span data-stu-id="90cc7-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90cc7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="90cc7-104">Methods</span></span>  
  
|<span data-ttu-id="90cc7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="90cc7-105">Method</span></span>|<span data-ttu-id="90cc7-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90cc7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90cc7-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="90cc7-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="90cc7-108">Ruft die RVAs der angegebenen Anzahl von Objekten aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="90cc7-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90cc7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90cc7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90cc7-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="90cc7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90cc7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90cc7-111">Requirements</span></span>  

 <span data-ttu-id="90cc7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90cc7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90cc7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90cc7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90cc7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90cc7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90cc7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cc7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cc7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90cc7-116">See also</span></span>

- [<span data-ttu-id="90cc7-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="90cc7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
