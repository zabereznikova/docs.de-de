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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396927"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="1b1d1-102">Isosdacinterface:: getmethoddescptrfromip-Methode</span><span class="sxs-lookup"><span data-stu-id="1b1d1-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="1b1d1-103">Ruft den Zeiger von MethodDesc entsprechend der Methode ab, die die angegebene Native Anweisungs Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="1b1d1-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1b1d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b1d1-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="1b1d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b1d1-105">Parameters</span></span>

`ip`\
<span data-ttu-id="1b1d1-106">in Eine Adresse innerhalb der Methode zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1b1d1-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="1b1d1-107">vorgenommen Die Adresse der `MethodDesc` für die jeweilige Methode.</span><span class="sxs-lookup"><span data-stu-id="1b1d1-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b1d1-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1b1d1-108">Remarks</span></span>

<span data-ttu-id="1b1d1-109">Die bereitgestellte Methode ist Teil der- [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und entspricht dem 22. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="1b1d1-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b1d1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b1d1-110">Requirements</span></span>

<span data-ttu-id="1b1d1-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b1d1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1b1d1-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="1b1d1-112">**Header:** None</span></span>  
<span data-ttu-id="1b1d1-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="1b1d1-113">**Library:** None</span></span>  
<span data-ttu-id="1b1d1-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1b1d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1b1d1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b1d1-115">See also</span></span>

- [<span data-ttu-id="1b1d1-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1b1d1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="1b1d1-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b1d1-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
