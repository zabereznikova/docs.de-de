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
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111682"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="f8cfa-102">DacpGetModuleAddress::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="f8cfa-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="f8cfa-103">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="f8cfa-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f8cfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8cfa-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="f8cfa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8cfa-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="f8cfa-106">[in] Ein Zeiger auf die Seed-Data-Modul.</span><span class="sxs-lookup"><span data-stu-id="f8cfa-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8cfa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8cfa-107">Remarks</span></span>

<span data-ttu-id="f8cfa-108">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f8cfa-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f8cfa-109">Um es zu verwenden, ist die einfachste Möglichkeit, um die Implementierung zu imitieren:</span><span class="sxs-lookup"><span data-stu-id="f8cfa-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="f8cfa-110">Rückgabewert von Aufrufen der `Request` Methode für die `IXCLRDataModule*` Parameter mit den folgenden Parametern: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="f8cfa-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="f8cfa-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8cfa-111">Requirements</span></span>

<span data-ttu-id="f8cfa-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8cfa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f8cfa-113">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="f8cfa-113">**Header:** None</span></span>     
<span data-ttu-id="f8cfa-114">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="f8cfa-114">**Library:** None</span></span>  
<span data-ttu-id="f8cfa-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8cfa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f8cfa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8cfa-116">See also</span></span>

- [<span data-ttu-id="f8cfa-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f8cfa-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="f8cfa-118">DacpGetModuleAddress-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8cfa-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)