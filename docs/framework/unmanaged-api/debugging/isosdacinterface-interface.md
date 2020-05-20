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
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420967"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="36c29-102">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36c29-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="36c29-103">Stellt Hilfsmethoden für den Zugriff auf Daten aus bereit `SOS` .</span><span class="sxs-lookup"><span data-stu-id="36c29-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="36c29-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="36c29-104">Methods</span></span>

| <span data-ttu-id="36c29-105">Methode</span><span class="sxs-lookup"><span data-stu-id="36c29-105">Method</span></span>                                                                                                               | <span data-ttu-id="36c29-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="36c29-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="36c29-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="36c29-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="36c29-108">Ruft die Daten für den angegebenen methodde-Zeiger ab.</span><span class="sxs-lookup"><span data-stu-id="36c29-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="36c29-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="36c29-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="36c29-110">Ruft den Zeiger von MethodDesc entsprechend der Methode ab, die die angegebene Native Anweisungs Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="36c29-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="36c29-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="36c29-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="36c29-112">Ruft die Daten ab, die dem Modul entsprechen, das an einer bestimmten Adresse geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="36c29-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="36c29-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36c29-113">Remarks</span></span>

<span data-ttu-id="36c29-114">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="36c29-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="36c29-115">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `436f00f2-b42a-4b9f-870c-e73db66ae930` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="36c29-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="36c29-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36c29-116">Requirements</span></span>

<span data-ttu-id="36c29-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c29-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="36c29-118">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="36c29-118">**Header:** None</span></span>  
<span data-ttu-id="36c29-119">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="36c29-119">**Library:** None</span></span>  
<span data-ttu-id="36c29-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36c29-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="36c29-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36c29-121">See also</span></span>

- [<span data-ttu-id="36c29-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="36c29-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="36c29-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="36c29-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
