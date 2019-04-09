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
ms.openlocfilehash: f62cbdc4b3e73f0c27492f7ed20b35378654d399
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152957"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="e4f32-102">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4f32-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="e4f32-103">Stellt Methoden zum Abfragen von Informationen zu einer Methodeninstanz bereit.</span><span class="sxs-lookup"><span data-stu-id="e4f32-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e4f32-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e4f32-104">Methods</span></span>

| <span data-ttu-id="e4f32-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e4f32-105">Method</span></span>                                                                                                                  | <span data-ttu-id="e4f32-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4f32-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="e4f32-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="e4f32-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="e4f32-108">Ruft den IL-Code mit Adressinformationen für die Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="e4f32-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="e4f32-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="e4f32-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="e4f32-110">Ruft die Adresse der repräsentativsten Eintrag für die systemeigene Kompilierung alle möglichen Einstiegspunkte für eine Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e4f32-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e4f32-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4f32-111">Remarks</span></span>

<span data-ttu-id="e4f32-112">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e4f32-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e4f32-113">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4f32-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4f32-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4f32-114">Requirements</span></span>

<span data-ttu-id="e4f32-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4f32-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4f32-116">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e4f32-116">**Header:** None</span></span>  
<span data-ttu-id="e4f32-117">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e4f32-117">**Library:** None</span></span>  
**<span data-ttu-id="e4f32-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e4f32-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="e4f32-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4f32-119">See also</span></span>

- [<span data-ttu-id="e4f32-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e4f32-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="e4f32-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e4f32-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
