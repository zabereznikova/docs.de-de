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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199374"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="7feab-102">ICorDebugFunction2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7feab-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="7feab-103">Erweitert logisch die ICorDebugFunction-Schnittstelle und unterstützt nur mein Code Debuggen in ausführlichen Schritten, die nicht benutzerseitiger Code überspringt.</span><span class="sxs-lookup"><span data-stu-id="7feab-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7feab-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7feab-104">Methods</span></span>  
  
|<span data-ttu-id="7feab-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7feab-105">Method</span></span>|<span data-ttu-id="7feab-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7feab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7feab-107">EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="7feab-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="7feab-108">(Noch nicht implementiert.) Ruft einen Schnittstellenzeiger auf ein ICorDebugCodeEnum mit den nativen codeanweisungen in der Funktion, die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7feab-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="7feab-109">GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="7feab-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="7feab-110">Ruft einen Wert, der angibt, ob diese Funktion als Benutzercode markiert ist.</span><span class="sxs-lookup"><span data-stu-id="7feab-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="7feab-111">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="7feab-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="7feab-112">Ruft die bearbeiten und Fortfahren-Version dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="7feab-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="7feab-113">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="7feab-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="7feab-114">Wird von dieser Funktion für nur mein Code schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="7feab-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7feab-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7feab-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7feab-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7feab-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7feab-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7feab-117">Requirements</span></span>  
 <span data-ttu-id="7feab-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7feab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7feab-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7feab-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7feab-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7feab-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7feab-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7feab-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7feab-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7feab-122">See also</span></span>

- [<span data-ttu-id="7feab-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7feab-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
