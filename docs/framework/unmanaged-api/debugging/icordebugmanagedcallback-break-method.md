---
title: ICorDebugManagedCallback::Break-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122582"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="147da-102">ICorDebugManagedCallback::Break-Methode</span><span class="sxs-lookup"><span data-stu-id="147da-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="147da-103">Benachrichtigt den Debugger, wenn eine <xref:System.Reflection.Emit.OpCodes.Break> Anweisung im Codestream ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="147da-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="147da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="147da-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="147da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="147da-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="147da-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die Break-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="147da-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="147da-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der die Break-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="147da-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="147da-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="147da-108">Requirements</span></span>

<span data-ttu-id="147da-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="147da-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="147da-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="147da-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="147da-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="147da-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="147da-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="147da-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="147da-113">See also</span></span>

- [<span data-ttu-id="147da-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="147da-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
