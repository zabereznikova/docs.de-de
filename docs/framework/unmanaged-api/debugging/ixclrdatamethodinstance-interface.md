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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790408"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="a9a4a-102">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a4a-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="a9a4a-103">Stellt Methoden bereit, mit denen Informationen zu einer Methoden Instanz abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="a9a4a-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a9a4a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a9a4a-104">Methods</span></span>

| <span data-ttu-id="a9a4a-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="a9a4a-105">Method</span></span>                                                                                                                  | <span data-ttu-id="a9a4a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9a4a-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="a9a4a-107">Getiladdressmap</span><span class="sxs-lookup"><span data-stu-id="a9a4a-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="a9a4a-108">Ruft die Il zum Adressieren von Zuordnungsinformationen ab</span><span class="sxs-lookup"><span data-stu-id="a9a4a-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="a9a4a-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="a9a4a-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="a9a4a-110">Ruft die für die systeminterne Kompilierung aller möglichen Einstiegspunkte einer Methode die am meisten repräsentative Einstiegspunkt Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="a9a4a-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a9a4a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9a4a-111">Remarks</span></span>

<span data-ttu-id="a9a4a-112">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="a9a4a-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a9a4a-113">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a9a4a-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a9a4a-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9a4a-114">Requirements</span></span>

<span data-ttu-id="a9a4a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a4a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a9a4a-116">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="a9a4a-116">**Header:** None</span></span>  
<span data-ttu-id="a9a4a-117">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="a9a4a-117">**Library:** None</span></span>  
<span data-ttu-id="a9a4a-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a4a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a9a4a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a4a-119">See also</span></span>

- [<span data-ttu-id="a9a4a-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a9a4a-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="a9a4a-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9a4a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
