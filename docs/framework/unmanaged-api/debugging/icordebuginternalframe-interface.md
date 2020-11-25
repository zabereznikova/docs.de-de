---
title: ICorDebugInternalFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: b7e738f06f9a9a06caedec2bdd0de4ab57f6d9b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719722"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="5b8c0-102">ICorDebugInternalFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b8c0-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="5b8c0-103">Stellt einen Lauf Zeit internen Frame im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="5b8c0-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b8c0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5b8c0-105">Methods</span></span>  
  
|<span data-ttu-id="5b8c0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5b8c0-106">Method</span></span>|<span data-ttu-id="5b8c0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b8c0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b8c0-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="5b8c0-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="5b8c0-109">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b8c0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b8c0-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b8c0-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b8c0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-112">Requirements</span></span>  

 <span data-ttu-id="5b8c0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b8c0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b8c0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b8c0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b8c0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b8c0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b8c0-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b8c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8c0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b8c0-117">See also</span></span>

- [<span data-ttu-id="5b8c0-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b8c0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
