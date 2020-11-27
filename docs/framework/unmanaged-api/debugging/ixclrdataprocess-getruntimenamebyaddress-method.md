---
title: 'Ixclrdataprocess:: getruntimenamebyaddress-Methode'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275566"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="37791-102">Ixclrdataprocess:: getruntimenamebyaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="37791-102">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="37791-103">Ruft einen Namen für die angegebene Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="37791-103">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="37791-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37791-104">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="37791-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37791-105">Parameters</span></span>

`address`\
<span data-ttu-id="37791-106">in Ein- `CLRDATA_ADDRESS` Wert, der eine Code Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="37791-106">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="37791-107">in Auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37791-107">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="37791-108">in Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="37791-108">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="37791-109">vorgenommen Ein Zeiger auf die Anzahl der zurückgegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="37791-109">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="37791-110">[out, size_is ( `bufLen` )] der Eingabepuffer der Länge `bufLen` , in der der Lauf Zeit Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="37791-110">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="37791-111">vorgenommen Ein `CLRDATA_ADDRESS` Zeiger auf den Code Offset des zurückgegebenen Symbols.</span><span class="sxs-lookup"><span data-stu-id="37791-111">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="37791-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37791-112">Remarks</span></span>

<span data-ttu-id="37791-113">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 16. Slot der Virtual-Method-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37791-113">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="37791-114">Wenn der Puffer nicht groß genug für den Namen ist, gibt diese Methode zurück `S_FALSE` und legt `nameLen` auf die erforderliche Pufferlänge fest.</span><span class="sxs-lookup"><span data-stu-id="37791-114">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="37791-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37791-115">Requirements</span></span>

<span data-ttu-id="37791-116">**Plattformen:** Siehe [System Anforderungen](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="37791-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="37791-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="37791-117">**Header:** None\</span></span>
<span data-ttu-id="37791-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="37791-118">**Library:** None\</span></span>
<span data-ttu-id="37791-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37791-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="37791-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37791-120">See also</span></span>

- [<span data-ttu-id="37791-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="37791-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="37791-122">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37791-122">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
