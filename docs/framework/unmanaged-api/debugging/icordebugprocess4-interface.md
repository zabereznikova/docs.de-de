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
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213581"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="aeae8-102">ICorDebugProcess4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aeae8-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="aeae8-103">Bietet Unterstützung für die Out-of-Process-Ausführungs Steuerung.</span><span class="sxs-lookup"><span data-stu-id="aeae8-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="aeae8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="aeae8-104">Methods</span></span>

| <span data-ttu-id="aeae8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="aeae8-105">Method</span></span>                                                                 | <span data-ttu-id="aeae8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aeae8-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="aeae8-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="aeae8-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="aeae8-108">Benachrichtigt die ICorDebug-Pipeline, dass der Out-of-Process-Debugger die Ausführung des Debuggens fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="aeae8-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="aeae8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aeae8-109">Remarks</span></span>

<span data-ttu-id="aeae8-110">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="aeae8-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="aeae8-111">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="aeae8-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="aeae8-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aeae8-112">Requirements</span></span>

<span data-ttu-id="aeae8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeae8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="aeae8-114">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="aeae8-114">**Header:** None</span></span>

<span data-ttu-id="aeae8-115">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="aeae8-115">**Library:** None</span></span>

<span data-ttu-id="aeae8-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeae8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aeae8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aeae8-117">See also</span></span>

- [<span data-ttu-id="aeae8-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="aeae8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="aeae8-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="aeae8-119">Debugging</span></span>](index.md)
