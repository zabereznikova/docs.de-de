---
title: ICorDebugProcess4-Schnittstelle
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221425"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="7ebcc-102">ICorDebugProcess4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ebcc-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="7ebcc-103">Bietet Unterstützung für die Out-of ausführungssteuerung Prozess.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="7ebcc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ebcc-104">Methods</span></span>

| <span data-ttu-id="7ebcc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7ebcc-105">Method</span></span>                                                                 | <span data-ttu-id="7ebcc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ebcc-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="7ebcc-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="7ebcc-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="7ebcc-108">Benachrichtigt, dass die Out-of Prozess-Debugger, die zu debuggende Komponente Ausführung fortgesetzt wird der ICorDebug-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7ebcc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ebcc-109">Remarks</span></span>

<span data-ttu-id="7ebcc-110">Diese Schnittstelle befindet sich in der Common Language Runtime und wird nicht über alle Header oder Bibliotheksdateien verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="7ebcc-111">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ebcc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ebcc-112">Requirements</span></span>

<span data-ttu-id="7ebcc-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ebcc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7ebcc-114">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="7ebcc-114">**Header:** None</span></span>

<span data-ttu-id="7ebcc-115">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="7ebcc-115">**Library:** None</span></span>

<span data-ttu-id="7ebcc-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ebcc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ebcc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ebcc-117">See also</span></span>

- [<span data-ttu-id="7ebcc-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ebcc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7ebcc-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7ebcc-119">Debugging</span></span>](index.md)
