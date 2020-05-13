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
ms.openlocfilehash: 332bc99795c0a4c896b60c61941a5a24b3f4accc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209941"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="89085-102">ICorDebugInternalFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89085-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="89085-103">Stellt einen Lauf Zeit internen Frame im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="89085-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="89085-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="89085-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89085-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="89085-105">Methods</span></span>  
  
|<span data-ttu-id="89085-106">Methode</span><span class="sxs-lookup"><span data-stu-id="89085-106">Method</span></span>|<span data-ttu-id="89085-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89085-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89085-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="89085-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="89085-109">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="89085-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89085-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89085-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89085-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="89085-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89085-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89085-112">Requirements</span></span>  
 <span data-ttu-id="89085-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89085-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89085-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89085-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89085-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89085-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89085-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89085-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89085-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89085-117">See also</span></span>

- [<span data-ttu-id="89085-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="89085-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
