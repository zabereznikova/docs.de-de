---
title: IXCLRDataModule-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c8d6e36687fd43bbc59304eee64dd42eb78101e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676522"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="d2884-102">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2884-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="d2884-103">Stellt Methoden zum Abfragen von Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="d2884-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="d2884-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d2884-104">Methods</span></span>

| <span data-ttu-id="d2884-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d2884-105">Method</span></span>                                                                                                                                | <span data-ttu-id="d2884-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2884-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="d2884-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="d2884-107">GetMethodDefinitionByToken</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="d2884-108">Ruft die Definition der Methode für einen angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="d2884-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="d2884-109">Anforderung</span><span class="sxs-lookup"><span data-stu-id="d2884-109">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="d2884-110">Anforderungen zum Auffüllen mit Daten für das Modul des angegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="d2884-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="d2884-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="d2884-111">GetVersionId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="d2884-112">Ruft die Modul Versions-ID</span><span class="sxs-lookup"><span data-stu-id="d2884-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="d2884-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2884-113">Remarks</span></span>

<span data-ttu-id="d2884-114">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="d2884-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d2884-115">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d2884-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d2884-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2884-116">Requirements</span></span>

<span data-ttu-id="d2884-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2884-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d2884-118">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="d2884-118">**Header:** None</span></span>  
<span data-ttu-id="d2884-119">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="d2884-119">**Library:** None</span></span>  
<span data-ttu-id="d2884-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d2884-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d2884-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2884-121">See also</span></span>

- [<span data-ttu-id="d2884-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d2884-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d2884-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2884-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
