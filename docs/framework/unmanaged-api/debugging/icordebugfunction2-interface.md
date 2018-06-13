---
title: ICorDebugFunction2 Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d765f87e36c98b5f664e84d85b883bc949fccf54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415333"
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="56346-102">ICorDebugFunction2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="56346-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="56346-103">Erweitert logisch die ICorDebugFunction-Schnittstelle und unterstützt nur mein Code schrittweisen Debuggen, die nicht-benutzerseitigen Code übersprungen.</span><span class="sxs-lookup"><span data-stu-id="56346-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56346-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="56346-104">Methods</span></span>  
  
|<span data-ttu-id="56346-105">Methode</span><span class="sxs-lookup"><span data-stu-id="56346-105">Method</span></span>|<span data-ttu-id="56346-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56346-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56346-107">EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="56346-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="56346-108">(Noch nicht implementiert.) Ruft einen Schnittstellenzeiger auf eine ICorDebugCodeEnum mit den systemeigenen codeanweisungen in der Funktion, die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="56346-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="56346-109">GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="56346-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="56346-110">Ruft einen Wert, der angibt, ob diese Funktion als Benutzercode markiert ist.</span><span class="sxs-lookup"><span data-stu-id="56346-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="56346-111">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="56346-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="56346-112">Ruft die Version dieser Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="56346-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="56346-113">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="56346-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="56346-114">Markiert diese Funktion für nur mein Code schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="56346-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56346-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56346-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56346-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="56346-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56346-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56346-117">Requirements</span></span>  
 <span data-ttu-id="56346-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56346-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56346-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56346-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56346-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56346-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56346-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56346-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56346-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56346-122">See Also</span></span>  
 [<span data-ttu-id="56346-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="56346-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
