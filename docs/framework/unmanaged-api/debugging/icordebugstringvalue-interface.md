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
ms.openlocfilehash: 6c232163f7c18086804eca7990a0890a507ef00b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791687"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="1afcb-102">ICorDebugStringValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1afcb-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="1afcb-103">Eine Unterklasse von ICorDebugHeapValue, die auf Zeichen folgen Werte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1afcb-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1afcb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1afcb-104">Methods</span></span>  
  
|<span data-ttu-id="1afcb-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="1afcb-105">Method</span></span>|<span data-ttu-id="1afcb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1afcb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1afcb-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="1afcb-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="1afcb-108">Ruft die Anzahl der Zeichen in der Zeichenfolge ab, auf die von diesem `ICorDebugStringValue`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1afcb-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="1afcb-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="1afcb-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="1afcb-110">Ruft die Zeichenfolge ab, auf die diese `ICorDebugStringValue`verweist.</span><span class="sxs-lookup"><span data-stu-id="1afcb-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1afcb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1afcb-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1afcb-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1afcb-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1afcb-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1afcb-113">Requirements</span></span>  
 <span data-ttu-id="1afcb-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1afcb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1afcb-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1afcb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1afcb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1afcb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1afcb-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1afcb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afcb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1afcb-118">See also</span></span>

- [<span data-ttu-id="1afcb-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1afcb-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
