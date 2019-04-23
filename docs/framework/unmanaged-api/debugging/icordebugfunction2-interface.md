---
title: ICorDebugFunction2-Schnittstelle
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
ms.openlocfilehash: 159cebc76f732629ed84a3b6c9041cc15f8bbb69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199374"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="17bbf-102">ICorDebugFunction2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17bbf-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="17bbf-103">Erweitert logisch die ICorDebugFunction-Schnittstelle und unterstützt nur mein Code Debuggen in ausführlichen Schritten, die nicht benutzerseitiger Code überspringt.</span><span class="sxs-lookup"><span data-stu-id="17bbf-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17bbf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="17bbf-104">Methods</span></span>  
  
|<span data-ttu-id="17bbf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="17bbf-105">Method</span></span>|<span data-ttu-id="17bbf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17bbf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17bbf-107">EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="17bbf-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="17bbf-108">(Noch nicht implementiert.) Ruft einen Schnittstellenzeiger auf ein ICorDebugCodeEnum mit den nativen codeanweisungen in der Funktion, die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="17bbf-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="17bbf-109">GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="17bbf-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="17bbf-110">Ruft einen Wert, der angibt, ob diese Funktion als Benutzercode markiert ist.</span><span class="sxs-lookup"><span data-stu-id="17bbf-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="17bbf-111">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="17bbf-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="17bbf-112">Ruft die bearbeiten und Fortfahren-Version dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="17bbf-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="17bbf-113">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="17bbf-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="17bbf-114">Wird von dieser Funktion für nur mein Code schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="17bbf-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17bbf-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17bbf-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17bbf-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="17bbf-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17bbf-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17bbf-117">Requirements</span></span>  
 <span data-ttu-id="17bbf-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17bbf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17bbf-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17bbf-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17bbf-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17bbf-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17bbf-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17bbf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17bbf-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17bbf-122">See also</span></span>

- [<span data-ttu-id="17bbf-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="17bbf-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
