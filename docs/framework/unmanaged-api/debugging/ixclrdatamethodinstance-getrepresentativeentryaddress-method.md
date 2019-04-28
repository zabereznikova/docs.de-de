---
title: IXCLRDataMethodInstance::GetRepresentativeEntryAddress-Methode
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 6f204e2ed9cb1409d53432355467bb11946f8809
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775530"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="904bc-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="904bc-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="904bc-103">Ruft die Adresse der repräsentativsten Eintrag für die systemeigene Kompilierung alle möglichen Einstiegspunkte für eine Methode ab.</span><span class="sxs-lookup"><span data-stu-id="904bc-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="904bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="904bc-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="904bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="904bc-105">Parameters</span></span>

`addr`\
<span data-ttu-id="904bc-106">[out] Die Adresse des dem repräsentativsten systemeigener Einstiegspunkt für die Methode.</span><span class="sxs-lookup"><span data-stu-id="904bc-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="904bc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="904bc-107">Remarks</span></span>

<span data-ttu-id="904bc-108">Die angegebene Methode ist Teil der [ `IXCLRDataMethodInstance` Schnittstelle](ixclrdatamethodinstance-interface.md) und mit dem 19. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="904bc-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="904bc-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="904bc-109">Requirements</span></span>

<span data-ttu-id="904bc-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="904bc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="904bc-111">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="904bc-111">**Header:** None</span></span>  
<span data-ttu-id="904bc-112">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="904bc-112">**Library:** None</span></span>  
<span data-ttu-id="904bc-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="904bc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="904bc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="904bc-114">See also</span></span>

- [<span data-ttu-id="904bc-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="904bc-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="904bc-116">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="904bc-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
