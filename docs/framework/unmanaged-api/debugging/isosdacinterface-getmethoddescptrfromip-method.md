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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922758"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="e7b45-102">ISOSDacInterface::GetMethodDescPtrFromIP-Methode</span><span class="sxs-lookup"><span data-stu-id="e7b45-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="e7b45-103">Ruft ab, der Zeiger für die MethodDesc entspricht die Methode, die mit dem angegebenen systemeigenen Anweisungsadresse.</span><span class="sxs-lookup"><span data-stu-id="e7b45-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e7b45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7b45-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="e7b45-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7b45-105">Parameters</span></span>

`ip`\
<span data-ttu-id="e7b45-106">[in] Eine Adresse innerhalb der Methode zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="e7b45-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="e7b45-107">[out] Die Adresse der `MethodDesc` für die jeweilige Methode.</span><span class="sxs-lookup"><span data-stu-id="e7b45-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7b45-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7b45-108">Remarks</span></span>

<span data-ttu-id="e7b45-109">Die angegebene Methode ist Teil der [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und mit dem 21. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="e7b45-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e7b45-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7b45-110">Requirements</span></span>

<span data-ttu-id="e7b45-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7b45-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e7b45-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e7b45-112">**Header:** None</span></span>  
<span data-ttu-id="e7b45-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e7b45-113">**Library:** None</span></span>  
<span data-ttu-id="e7b45-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e7b45-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e7b45-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7b45-115">See also</span></span>

- [<span data-ttu-id="e7b45-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e7b45-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="e7b45-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7b45-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)