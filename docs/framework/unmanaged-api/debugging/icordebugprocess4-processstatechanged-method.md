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
ms.openlocfilehash: b434f30fc187af8b118ac926fec96d28182b0bfc
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221432"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="961ae-102">ICorDebugProcess4::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="961ae-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="961ae-103">Benachrichtigt, dass die Out-of Prozess-Debugger, die zu debuggende Komponente Ausführung fortgesetzt wird der ICorDebug-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="961ae-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="961ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="961ae-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

#### <a name="parameters"></a><span data-ttu-id="961ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="961ae-105">Parameters</span></span>

 `eChange`

 <span data-ttu-id="961ae-106">[in] Ein Mitglied der [CorDebugStateChange-Enumeration](cordebugstatechange-enumeration.md) , beschreibt eine Änderung im Ausführungsstatus des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="961ae-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="961ae-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="961ae-107">Remarks</span></span>

<span data-ttu-id="961ae-108">Die angegebene Methode ist Teil der `ICorDebugProcess4` Schnittstelle, und mit dem vierten Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="961ae-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="961ae-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="961ae-109">Requirements</span></span>

 <span data-ttu-id="961ae-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="961ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="961ae-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="961ae-111">**Header:** None</span></span>

 <span data-ttu-id="961ae-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="961ae-112">**Library:** None</span></span>
 
 <span data-ttu-id="961ae-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="961ae-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="961ae-114">See also</span></span>

- [<span data-ttu-id="961ae-115">ICorDebugProcess4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961ae-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="961ae-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="961ae-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="961ae-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="961ae-117">Debugging</span></span>](index.md)
