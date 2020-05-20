---
title: 'Isosdacinterface:: getmethoddescptrfromip-Methode'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c3de9e5ffe23a13c126343c6f74f042bf1239609
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421006"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="dfcc7-102">Isosdacinterface:: getmethoddescptrfromip-Methode</span><span class="sxs-lookup"><span data-stu-id="dfcc7-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="dfcc7-103">Ruft den Zeiger von MethodDesc entsprechend der Methode ab, die die angegebene Native Anweisungs Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dfcc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfcc7-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="dfcc7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfcc7-105">Parameters</span></span>

`ip`\
<span data-ttu-id="dfcc7-106">in Eine Adresse innerhalb der Methode zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="dfcc7-107">vorgenommen Die Adresse der `MethodDesc` für die jeweilige Methode.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfcc7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfcc7-108">Remarks</span></span>

<span data-ttu-id="dfcc7-109">Die bereitgestellte Methode ist Teil der- [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und entspricht dem 22. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dfcc7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfcc7-110">Requirements</span></span>

<span data-ttu-id="dfcc7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfcc7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dfcc7-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="dfcc7-112">**Header:** None</span></span>  
<span data-ttu-id="dfcc7-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="dfcc7-113">**Library:** None</span></span>  
<span data-ttu-id="dfcc7-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dfcc7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dfcc7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfcc7-115">See also</span></span>

- [<span data-ttu-id="dfcc7-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="dfcc7-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="dfcc7-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfcc7-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
