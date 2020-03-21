---
title: DacpGetModuleAddress::Anforderungsmethode
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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179199"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="9a8e3-102">DacpGetModuleAddress::Anforderungsmethode</span><span class="sxs-lookup"><span data-stu-id="9a8e3-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="9a8e3-103">Führt eine Anforderung aus, um die Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="9a8e3-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9a8e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a8e3-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="9a8e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a8e3-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="9a8e3-106">[in] Ein Zeiger auf das Seed-Datenmodul.</span><span class="sxs-lookup"><span data-stu-id="9a8e3-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a8e3-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9a8e3-107">Remarks</span></span>

<span data-ttu-id="9a8e3-108">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9a8e3-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9a8e3-109">Um es zu verwenden, ist der einfachste Weg, die Implementierung nachzuahmen:</span><span class="sxs-lookup"><span data-stu-id="9a8e3-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="9a8e3-110">Geben Sie den Wert `Request` zurück, `IXCLRDataModule*` der durch Aufrufen der Methode für den Parameter mit den folgenden Parametern erhalten wurde:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="9a8e3-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="9a8e3-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9a8e3-111">Requirements</span></span>

<span data-ttu-id="9a8e3-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a8e3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9a8e3-113">**Kopfzeile:** Keine **Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="9a8e3-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="9a8e3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8e3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a8e3-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a8e3-115">See also</span></span>

- [<span data-ttu-id="9a8e3-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9a8e3-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="9a8e3-117">DacpGetModuleAddress-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a8e3-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
