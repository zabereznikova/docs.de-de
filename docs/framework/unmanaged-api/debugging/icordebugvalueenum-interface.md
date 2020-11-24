---
title: ICorDebugValueEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: e3934cbce76df3997fa07d8fa3a99bd8ddab09a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684342"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="1cc48-102">ICorDebugValueEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1cc48-102">ICorDebugValueEnum Interface</span></span>

<span data-ttu-id="1cc48-103">Implementiert die ICorDebugEnum-Methoden und listet die ICorDebugValue-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1cc48-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cc48-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1cc48-104">Methods</span></span>  
  
|<span data-ttu-id="1cc48-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1cc48-105">Method</span></span>|<span data-ttu-id="1cc48-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1cc48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1cc48-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="1cc48-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="1cc48-108">Ruft die angegebene Anzahl von- `ICorDebugValue` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="1cc48-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cc48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cc48-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cc48-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1cc48-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc48-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1cc48-111">Requirements</span></span>  

 <span data-ttu-id="1cc48-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc48-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc48-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cc48-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cc48-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cc48-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cc48-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc48-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cc48-116">See also</span></span>

- [<span data-ttu-id="1cc48-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1cc48-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
