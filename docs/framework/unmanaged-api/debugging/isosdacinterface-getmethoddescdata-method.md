---
title: 'Isosdacinterface:: getmethoddescdata-Methode'
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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396947"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="7e68d-102">Isosdacinterface:: getmethoddescdata-Methode</span><span class="sxs-lookup"><span data-stu-id="7e68d-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="7e68d-103">Ruft die Daten für den angegebenen methodde-Zeiger ab.</span><span class="sxs-lookup"><span data-stu-id="7e68d-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7e68d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e68d-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="7e68d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e68d-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="7e68d-106">in Die Adresse von methoddebug.</span><span class="sxs-lookup"><span data-stu-id="7e68d-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="7e68d-107">in Die IP-Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="7e68d-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="7e68d-108">vorgenommen Die der methoddebug zugeordneten Daten, die von den internen APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7e68d-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="7e68d-109">vorgenommen Die Anzahl der zurückgesetzten ReJIT-Versionen.</span><span class="sxs-lookup"><span data-stu-id="7e68d-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="7e68d-110">vorgenommen Die Daten, die den wiederhergestellten ReJIT-Versionen zugeordnet sind, die von den internen APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7e68d-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="7e68d-111">vorgenommen Die Anzahl der Bytes, die erforderlich sind, um die Daten zu speichern, die den wiederhergestellten ReJIT-Versionen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7e68d-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e68d-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e68d-112">Remarks</span></span>

<span data-ttu-id="7e68d-113">Die bereitgestellte Methode ist Teil der `ISOSDacInterface` -Schnittstelle und entspricht dem 21. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="7e68d-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="7e68d-114">Um Sie verwenden zu können, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) muss als eine 64-Bit-Ganzzahl ohne Vorzeichen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e68d-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e68d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e68d-115">Requirements</span></span>

<span data-ttu-id="7e68d-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e68d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7e68d-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="7e68d-117">**Header:** None</span></span>  
<span data-ttu-id="7e68d-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="7e68d-118">**Library:** None</span></span>  
<span data-ttu-id="7e68d-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e68d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7e68d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e68d-120">See also</span></span>

- [<span data-ttu-id="7e68d-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7e68d-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="7e68d-122">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e68d-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
