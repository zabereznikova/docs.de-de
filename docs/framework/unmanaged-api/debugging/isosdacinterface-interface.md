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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922147"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="0b907-102">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b907-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="0b907-103">Stellt Hilfsmethoden bereit, um den Zugriff auf Daten aus `SOS`.</span><span class="sxs-lookup"><span data-stu-id="0b907-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="0b907-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0b907-104">Methods</span></span>

| <span data-ttu-id="0b907-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0b907-105">Method</span></span>                                                                                                               | <span data-ttu-id="0b907-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b907-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="0b907-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="0b907-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="0b907-108">Ruft die Daten für den angegebenen MethodDesc-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="0b907-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="0b907-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="0b907-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="0b907-110">Ruft ab, der Zeiger für die MethodDesc entspricht die Methode, die mit dem angegebenen systemeigenen Anweisungsadresse.</span><span class="sxs-lookup"><span data-stu-id="0b907-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="0b907-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="0b907-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="0b907-112">Die Daten, die für das Modul geladen, die an einer bestimmten Adresse abruft.</span><span class="sxs-lookup"><span data-stu-id="0b907-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0b907-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b907-113">Remarks</span></span>

<span data-ttu-id="0b907-114">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="0b907-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0b907-115">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b907-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b907-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b907-116">Requirements</span></span>

<span data-ttu-id="0b907-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b907-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0b907-118">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="0b907-118">**Header:** None</span></span>  
<span data-ttu-id="0b907-119">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="0b907-119">**Library:** None</span></span>  
<span data-ttu-id="0b907-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b907-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0b907-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b907-121">See also</span></span>

- [<span data-ttu-id="0b907-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0b907-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0b907-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0b907-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
