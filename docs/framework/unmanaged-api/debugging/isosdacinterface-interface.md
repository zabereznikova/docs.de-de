---
title: ISOSDacInterface-Schnittstelle
ms.date: 01/16/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5e037cf6fb88fff4886733ff4152dca0a827e0a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491027"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="11b22-102">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11b22-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="11b22-103">Stellt Hilfsmethoden bereit, um den Zugriff auf Daten aus `SOS`.</span><span class="sxs-lookup"><span data-stu-id="11b22-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="11b22-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="11b22-104">Methods</span></span>

| <span data-ttu-id="11b22-105">Methode</span><span class="sxs-lookup"><span data-stu-id="11b22-105">Method</span></span>                                                                                                               | <span data-ttu-id="11b22-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11b22-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="11b22-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="11b22-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="11b22-108">Ruft ab, die Daten für den angegebenen [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="11b22-108">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span> |

## <a name="remarks"></a><span data-ttu-id="11b22-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11b22-109">Remarks</span></span>

<span data-ttu-id="11b22-110">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="11b22-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="11b22-111">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="11b22-111">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="11b22-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11b22-112">Requirements</span></span>

<span data-ttu-id="11b22-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11b22-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="11b22-114">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="11b22-114">**Header:** None</span></span>  
<span data-ttu-id="11b22-115">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="11b22-115">**Library:** None</span></span>  
<span data-ttu-id="11b22-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11b22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="11b22-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11b22-117">See also</span></span>

- [<span data-ttu-id="11b22-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="11b22-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="11b22-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="11b22-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
