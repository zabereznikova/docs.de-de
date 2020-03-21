---
title: ICorDebugProcess4::ProcessStateChanged-Methode
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
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178627"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="8b45c-102">ICorDebugProcess4::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="8b45c-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="8b45c-103">Benachrichtigt die ICorDebug-Pipeline, dass der Fehlerdebugger out of process die Ausführung des Debugees fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="8b45c-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b45c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b45c-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="8b45c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b45c-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="8b45c-106">[in] Ein Member der [CorDebugStateChange-Enumeration,](cordebugstatechange-enumeration.md) der eine Änderung im Ausführungsstatus des Prozesses beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8b45c-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b45c-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8b45c-107">Remarks</span></span>

<span data-ttu-id="8b45c-108">Die bereitgestellte Methode `ICorDebugProcess4` ist Teil der Schnittstelle und entspricht dem vierten Steckplatz der virtuellen Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="8b45c-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b45c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b45c-109">Requirements</span></span>

 <span data-ttu-id="8b45c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b45c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8b45c-111">**Kopfzeile:** nichts</span><span class="sxs-lookup"><span data-stu-id="8b45c-111">**Header:** None</span></span>

 <span data-ttu-id="8b45c-112">**Bibliothek:** nichts</span><span class="sxs-lookup"><span data-stu-id="8b45c-112">**Library:** None</span></span>

 <span data-ttu-id="8b45c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b45c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8b45c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b45c-114">See also</span></span>

- [<span data-ttu-id="8b45c-115">ICorDebugProcess4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b45c-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="8b45c-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8b45c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8b45c-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8b45c-117">Debugging</span></span>](index.md)
