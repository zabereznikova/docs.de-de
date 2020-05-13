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
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376196"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="58b22-102">ICorDebugStringValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58b22-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="58b22-103">Eine Unterklasse von ICorDebugHeapValue, die auf Zeichen folgen Werte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="58b22-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58b22-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="58b22-104">Methods</span></span>  
  
|<span data-ttu-id="58b22-105">Methode</span><span class="sxs-lookup"><span data-stu-id="58b22-105">Method</span></span>|<span data-ttu-id="58b22-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58b22-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58b22-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="58b22-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="58b22-108">Ruft die Anzahl der Zeichen in der Zeichenfolge ab, auf die von diesem verwiesen wird `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="58b22-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="58b22-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="58b22-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="58b22-110">Ruft die Zeichenfolge ab, auf die von verwiesen wird `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="58b22-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58b22-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58b22-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58b22-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58b22-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b22-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58b22-113">Requirements</span></span>  
 <span data-ttu-id="58b22-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b22-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b22-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58b22-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58b22-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58b22-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58b22-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b22-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b22-118">See also</span></span>

- [<span data-ttu-id="58b22-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="58b22-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
