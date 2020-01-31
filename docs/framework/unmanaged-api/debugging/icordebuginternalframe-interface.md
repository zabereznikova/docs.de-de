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
ms.openlocfilehash: 6bc24450cdda2e3ed324256b53b2d137d1eb90e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788486"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="17a26-102">ICorDebugInternalFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17a26-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="17a26-103">Stellt einen Lauf Zeit internen Frame im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="17a26-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="17a26-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="17a26-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17a26-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="17a26-105">Methods</span></span>  
  
|<span data-ttu-id="17a26-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="17a26-106">Method</span></span>|<span data-ttu-id="17a26-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17a26-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17a26-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="17a26-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="17a26-109">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="17a26-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17a26-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17a26-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17a26-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="17a26-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a26-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17a26-112">Requirements</span></span>  
 <span data-ttu-id="17a26-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a26-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a26-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17a26-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17a26-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17a26-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17a26-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17a26-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a26-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17a26-117">See also</span></span>

- [<span data-ttu-id="17a26-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="17a26-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
