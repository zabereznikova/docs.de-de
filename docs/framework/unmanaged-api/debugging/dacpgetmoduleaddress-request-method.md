---
title: DacpGetModuleAddress::Request-Methode
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860837"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="2db2f-102">DacpGetModuleAddress::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="2db2f-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="2db2f-103">Führt eine Anforderung aus, um die-Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="2db2f-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2db2f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2db2f-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="2db2f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2db2f-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="2db2f-106">in Ein Zeiger auf das Seed Data-Modul.</span><span class="sxs-lookup"><span data-stu-id="2db2f-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="2db2f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2db2f-107">Remarks</span></span>

<span data-ttu-id="2db2f-108">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="2db2f-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2db2f-109">Um es zu verwenden, ist die einfachste Möglichkeit, die Implementierung zu imitieren:</span><span class="sxs-lookup"><span data-stu-id="2db2f-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="2db2f-110">Gibt den Wert zurück, der durch `Request` Aufrufen der- `IXCLRDataModule*` Methode für den-Parameter mit den folgenden Parametern abgerufen wurde:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="2db2f-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="2db2f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2db2f-111">Requirements</span></span>

<span data-ttu-id="2db2f-112">**Plattformen:** Siehe [System Anforderungen](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="2db2f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="2db2f-113">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="2db2f-113">**Header:** None\</span></span>
<span data-ttu-id="2db2f-114">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="2db2f-114">**Library:** None\</span></span>
<span data-ttu-id="2db2f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2db2f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2db2f-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2db2f-116">See also</span></span>

- [<span data-ttu-id="2db2f-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2db2f-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2db2f-118">Dacpgetmoduleaddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="2db2f-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
