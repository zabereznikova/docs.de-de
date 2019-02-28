---
title: ICorDebugStringValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cff85a77b113440c2274910cae8ef93419d1bc1b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965357"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="f1b74-102">ICorDebugStringValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1b74-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="f1b74-103">Eine Unterklasse von ICorDebugHeapValue, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="f1b74-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1b74-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f1b74-104">Methods</span></span>  
  
|<span data-ttu-id="f1b74-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f1b74-105">Method</span></span>|<span data-ttu-id="f1b74-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1b74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1b74-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="f1b74-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="f1b74-108">Ruft die Anzahl der Zeichen in der Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="f1b74-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="f1b74-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="f1b74-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="f1b74-110">Ruft die Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="f1b74-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1b74-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1b74-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1b74-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f1b74-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b74-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1b74-113">Requirements</span></span>  
 <span data-ttu-id="f1b74-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1b74-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b74-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1b74-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1b74-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b74-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b74-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b74-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b74-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1b74-118">See also</span></span>
- [<span data-ttu-id="f1b74-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f1b74-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
