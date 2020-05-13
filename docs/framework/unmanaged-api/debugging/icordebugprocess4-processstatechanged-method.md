---
title: ICorDebugProcess4::P rocess StateChanged-Methode
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213568"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="c608c-102">ICorDebugProcess4::P rocess StateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="c608c-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="c608c-103">Benachrichtigt die ICorDebug-Pipeline, dass der Out-of-Process-Debugger die Ausführung des Debuggens fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="c608c-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="c608c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c608c-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="c608c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c608c-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="c608c-106">in Ein Member der [cordebugstatechange-Enumeration](cordebugstatechange-enumeration.md) , die eine Änderung des Ausführungs Status des Prozesses beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c608c-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="c608c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c608c-107">Remarks</span></span>

<span data-ttu-id="c608c-108">Die bereitgestellte Methode ist Teil der `ICorDebugProcess4` -Schnittstelle und entspricht dem vierten Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="c608c-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c608c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c608c-109">Requirements</span></span>

 <span data-ttu-id="c608c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c608c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="c608c-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="c608c-111">**Header:** None</span></span>

 <span data-ttu-id="c608c-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="c608c-112">**Library:** None</span></span>

 <span data-ttu-id="c608c-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c608c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c608c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c608c-114">See also</span></span>

- [<span data-ttu-id="c608c-115">ICorDebugProcess4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c608c-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="c608c-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c608c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c608c-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c608c-117">Debugging</span></span>](index.md)
