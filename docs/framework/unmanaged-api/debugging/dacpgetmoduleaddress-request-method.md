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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102906"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="31a94-102">DacpGetModuleAddress::Anforderungsmethode</span><span class="sxs-lookup"><span data-stu-id="31a94-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="31a94-103">Führt eine Anforderung aus, um die Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="31a94-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="31a94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31a94-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="31a94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31a94-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="31a94-106">[in] Ein Zeiger auf das Seed-Datenmodul.</span><span class="sxs-lookup"><span data-stu-id="31a94-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="31a94-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="31a94-107">Remarks</span></span>

<span data-ttu-id="31a94-108">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="31a94-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="31a94-109">Um es zu verwenden, ist der einfachste Weg, die Implementierung nachzuahmen:</span><span class="sxs-lookup"><span data-stu-id="31a94-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="31a94-110">Geben Sie den Wert `Request` zurück, `IXCLRDataModule*` der durch Aufrufen der Methode für den Parameter mit den folgenden Parametern erhalten wurde:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="31a94-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="31a94-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31a94-111">Requirements</span></span>

<span data-ttu-id="31a94-112">**Plattformen:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="31a94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="31a94-113">**Kopfzeile:** Keine</span><span class="sxs-lookup"><span data-stu-id="31a94-113">**Header:** None\</span></span>
<span data-ttu-id="31a94-114">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="31a94-114">**Library:** None\</span></span>
<span data-ttu-id="31a94-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31a94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="31a94-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31a94-116">See also</span></span>

- [<span data-ttu-id="31a94-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="31a94-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="31a94-118">DacpGetModuleAddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="31a94-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
