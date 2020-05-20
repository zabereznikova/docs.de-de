---
title: IXCLRDataMethodInstance-Schnittstelle
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0b1c982b25af9edea76a038b4314b4bd608f07df
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420889"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="7c214-102">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c214-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="7c214-103">Stellt Methoden bereit, mit denen Informationen zu einer Methoden Instanz abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="7c214-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="7c214-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c214-104">Methods</span></span>

| <span data-ttu-id="7c214-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7c214-105">Method</span></span>                                                                                                                  | <span data-ttu-id="7c214-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7c214-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="7c214-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="7c214-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="7c214-108">Ruft die Il zum Adressieren von Zuordnungsinformationen ab</span><span class="sxs-lookup"><span data-stu-id="7c214-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="7c214-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="7c214-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="7c214-110">Ruft die für die systeminterne Kompilierung aller möglichen Einstiegspunkte einer Methode die am meisten repräsentative Einstiegspunkt Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="7c214-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7c214-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c214-111">Remarks</span></span>

<span data-ttu-id="7c214-112">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="7c214-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7c214-113">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c214-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c214-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c214-114">Requirements</span></span>

<span data-ttu-id="7c214-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c214-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7c214-116">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="7c214-116">**Header:** None</span></span>  
<span data-ttu-id="7c214-117">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="7c214-117">**Library:** None</span></span>  
<span data-ttu-id="7c214-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c214-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7c214-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c214-119">See also</span></span>

- [<span data-ttu-id="7c214-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7c214-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="7c214-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c214-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
