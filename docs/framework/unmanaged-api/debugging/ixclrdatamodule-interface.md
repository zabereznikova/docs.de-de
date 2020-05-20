---
title: IXCLRDataModule Interface-Schnittstelle
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
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420850"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="08153-102">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08153-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="08153-103">Stellt Methoden zum Abfragen von Informationen über ein geladenes Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="08153-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="08153-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="08153-104">Methods</span></span>

| <span data-ttu-id="08153-105">Methode</span><span class="sxs-lookup"><span data-stu-id="08153-105">Method</span></span>                                                                                                                                | <span data-ttu-id="08153-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="08153-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="08153-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="08153-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="08153-108">Ruft die Methoden Definition ab, die einem angegebenen Metadatentoken entspricht.</span><span class="sxs-lookup"><span data-stu-id="08153-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="08153-109">Anforderung</span><span class="sxs-lookup"><span data-stu-id="08153-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="08153-110">Fordert an, den mit den Modul Daten angegebenen Puffer aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="08153-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="08153-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="08153-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="08153-112">Ruft die Versions-ID des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="08153-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="08153-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08153-113">Remarks</span></span>

<span data-ttu-id="08153-114">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="08153-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="08153-115">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="08153-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="08153-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08153-116">Requirements</span></span>

<span data-ttu-id="08153-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08153-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="08153-118">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="08153-118">**Header:** None</span></span>  
<span data-ttu-id="08153-119">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="08153-119">**Library:** None</span></span>  
<span data-ttu-id="08153-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08153-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="08153-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08153-121">See also</span></span>

- [<span data-ttu-id="08153-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="08153-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="08153-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="08153-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
