---
title: ISOSDacInterface::GetMethodDescData-Methode
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e56f837c4d3362ec6e71030e4fb475df42b9fba4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639949"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="1c1c5-102">ISOSDacInterface::GetMethodDescData-Methode</span><span class="sxs-lookup"><span data-stu-id="1c1c5-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="1c1c5-103">Ruft ab, die Daten für den angegebenen [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1c1c5-103">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1c1c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c1c5-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a><span data-ttu-id="1c1c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c1c5-105">Parameters</span></span>

<span data-ttu-id="1c1c5-106">`methodDesc` [in] Die Adresse der MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-106">`methodDesc` [in] The address of the MethodDesc.</span></span>

<span data-ttu-id="1c1c5-107">`ip` [in] Die IP-Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-107">`ip` [in] The IP address of the method.</span></span>

<span data-ttu-id="1c1c5-108">`data` [out] Die Daten, die die MethodDesc zugeordnet, wie die internen APIs zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-108">`data` [out] The data associated with the MethodDesc as returned from the internal APIs.</span></span> <span data-ttu-id="1c1c5-109">Die Struktur benötigt mindestens 168 Bytes.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-109">The structure needs at least 168 bytes.</span></span>

<span data-ttu-id="1c1c5-110">`cRevertedRejitVersions` [out] Die Anzahl der wiederhergestellten Rejit-Versionen.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-110">`cRevertedRejitVersions` [out] The number of reverted rejit versions.</span></span>

<span data-ttu-id="1c1c5-111">`rgRevertedRejitData` [out] Die Daten, die die wiederhergestellten Rejit-Versionen zugeordnet, wie die internen APIs zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-111">`rgRevertedRejitData` [out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span> <span data-ttu-id="1c1c5-112">Die Struktur benötigt mindestens 24 Bytes.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-112">The structure needs at least 24 bytes.</span></span>

<span data-ttu-id="1c1c5-113">`pcNeededRevertedRejitData` [out] Die Anzahl der Bytes, die zum Speichern der Daten verknüpft, die mit den wiederhergestellten ReJit-Versionen ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-113">`pcNeededRevertedRejitData` [out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c1c5-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c1c5-114">Remarks</span></span>

<span data-ttu-id="1c1c5-115">Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-115">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="1c1c5-116">Auch die `CLRDATA_ADDRESS` sind 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="1c1c5-116">Also the `CLRDATA_ADDRESS` are 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c1c5-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c1c5-117">Requirements</span></span>

<span data-ttu-id="1c1c5-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c1c5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1c1c5-119">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="1c1c5-119">**Header:** None</span></span>  
<span data-ttu-id="1c1c5-120">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="1c1c5-120">**Library:** None</span></span>  
<span data-ttu-id="1c1c5-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1c1c5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1c1c5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c1c5-122">See also</span></span>

- [<span data-ttu-id="1c1c5-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1c1c5-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1c1c5-124">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c1c5-124">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
