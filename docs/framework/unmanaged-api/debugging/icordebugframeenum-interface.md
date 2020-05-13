---
title: ICorDebugFrameEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
ms.openlocfilehash: 4bc8d56bf116cd64e3e1c5d2238e557784c56711
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209590"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="ca88e-102">ICorDebugFrameEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca88e-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="ca88e-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugFrame-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="ca88e-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca88e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca88e-104">Methods</span></span>  
  
|<span data-ttu-id="ca88e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca88e-105">Method</span></span>|<span data-ttu-id="ca88e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca88e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca88e-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="ca88e-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="ca88e-108">Ruft die angegebene Anzahl von- `ICorDebugFrame` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="ca88e-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca88e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca88e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca88e-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ca88e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca88e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca88e-111">Requirements</span></span>  
 <span data-ttu-id="ca88e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca88e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca88e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca88e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca88e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca88e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca88e-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca88e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca88e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca88e-116">See also</span></span>

- [<span data-ttu-id="ca88e-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca88e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
