---
title: ISOSDacInterface-Schnittstelle
ms.date: 02/01/2019
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
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827928"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="bb996-102">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb996-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="bb996-103">Stellt Hilfsmethoden bereit, um den Zugriff auf Daten aus `SOS`.</span><span class="sxs-lookup"><span data-stu-id="bb996-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="bb996-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bb996-104">Methods</span></span>

| <span data-ttu-id="bb996-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bb996-105">Method</span></span>                                                                                                               | <span data-ttu-id="bb996-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb996-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="bb996-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="bb996-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="bb996-108">Ruft die Daten für den angegebenen MethodDesc-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bb996-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="bb996-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="bb996-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="bb996-110">Ruft ab, der Zeiger für die MethodDesc entspricht die Methode, die mit dem angegebenen systemeigenen Anweisungsadresse.</span><span class="sxs-lookup"><span data-stu-id="bb996-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="bb996-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="bb996-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="bb996-112">Die Daten, die für das Modul geladen, die an einer bestimmten Adresse abruft.</span><span class="sxs-lookup"><span data-stu-id="bb996-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="bb996-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb996-113">Remarks</span></span>

<span data-ttu-id="bb996-114">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="bb996-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="bb996-115">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb996-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb996-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb996-116">Requirements</span></span>

<span data-ttu-id="bb996-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb996-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bb996-118">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="bb996-118">**Header:** None</span></span>  
<span data-ttu-id="bb996-119">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="bb996-119">**Library:** None</span></span>  
<span data-ttu-id="bb996-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb996-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bb996-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb996-121">See also</span></span>

- [<span data-ttu-id="bb996-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bb996-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="bb996-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb996-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
