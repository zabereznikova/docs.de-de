---
title: ISOSDacInterface::GetMethodDescPtrFromIP-Methode
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
ms.openlocfilehash: 82c4531ac16e8b4bf7ac45bc01eb7128b9507ab5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358534"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="69fa2-102">ISOSDacInterface::GetMethodDescPtrFromIP-Methode</span><span class="sxs-lookup"><span data-stu-id="69fa2-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="69fa2-103">Ruft ab, der Zeiger für die MethodDesc entspricht die Methode, die mit dem angegebenen systemeigenen Anweisungsadresse.</span><span class="sxs-lookup"><span data-stu-id="69fa2-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="69fa2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69fa2-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="69fa2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="69fa2-105">Parameters</span></span>

`ip`\
<span data-ttu-id="69fa2-106">[in] Eine Adresse innerhalb der Methode zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="69fa2-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="69fa2-107">[out] Die Adresse der `MethodDesc` für die jeweilige Methode.</span><span class="sxs-lookup"><span data-stu-id="69fa2-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="69fa2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69fa2-108">Remarks</span></span>

<span data-ttu-id="69fa2-109">Die angegebene Methode ist Teil der [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und mit dem 21. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="69fa2-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="69fa2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69fa2-110">Requirements</span></span>

<span data-ttu-id="69fa2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69fa2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="69fa2-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="69fa2-112">**Header:** None</span></span>  
<span data-ttu-id="69fa2-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="69fa2-113">**Library:** None</span></span>  
<span data-ttu-id="69fa2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="69fa2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="69fa2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69fa2-115">See also</span></span>

- [<span data-ttu-id="69fa2-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="69fa2-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="69fa2-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69fa2-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)