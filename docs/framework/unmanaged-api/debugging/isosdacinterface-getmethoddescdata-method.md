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
ms.openlocfilehash: cdbf662c664d6c87b2fa17bcb10d735b0f573dd2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632318"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="b8183-102">ISOSDacInterface::GetMethodDescData-Methode</span><span class="sxs-lookup"><span data-stu-id="b8183-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="b8183-103">Ruft die Daten für den angegebenen MethodDesc-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b8183-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b8183-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8183-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="b8183-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8183-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="b8183-106">[in] Die Adresse der MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="b8183-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="b8183-107">[in] Die IP-Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="b8183-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="b8183-108">[out] Die Daten, die die MethodDesc zugeordnet, wie die internen APIs zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b8183-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="b8183-109">[out] Die Anzahl der wiederhergestellten Rejit-Versionen.</span><span class="sxs-lookup"><span data-stu-id="b8183-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="b8183-110">[out] Die Daten, die die wiederhergestellten Rejit-Versionen zugeordnet, wie die internen APIs zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b8183-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="b8183-111">[out] Die Anzahl der Bytes, die zum Speichern der Daten verknüpft, die mit den wiederhergestellten ReJit-Versionen ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b8183-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8183-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8183-112">Remarks</span></span>

<span data-ttu-id="b8183-113">Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="b8183-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="b8183-114">Zu deren Verwendung können [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) muss als eine 64-Bit-Ganzzahl ohne Vorzeichen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8183-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8183-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8183-115">Requirements</span></span>

<span data-ttu-id="b8183-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8183-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b8183-117">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="b8183-117">**Header:** None</span></span>  
<span data-ttu-id="b8183-118">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="b8183-118">**Library:** None</span></span>  
<span data-ttu-id="b8183-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8183-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b8183-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8183-120">See also</span></span>

- [<span data-ttu-id="b8183-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b8183-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="b8183-122">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8183-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
