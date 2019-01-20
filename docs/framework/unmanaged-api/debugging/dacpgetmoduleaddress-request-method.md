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
ms.openlocfilehash: 86a51605ad8ea8b394c5b8a5961f32e96baf9e58
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416425"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="78212-102">DacpGetModuleAddress::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="78212-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="78212-103">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="78212-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="78212-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78212-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

### <a name="parameters"></a><span data-ttu-id="78212-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78212-105">Parameters</span></span>

<span data-ttu-id="78212-106">`pDataModule` [in] Ein Zeiger auf die Seed-Data-Modul.</span><span class="sxs-lookup"><span data-stu-id="78212-106">`pDataModule` [in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="78212-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78212-107">Remarks</span></span>

<span data-ttu-id="78212-108">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="78212-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="78212-109">Um es zu verwenden, ist die einfachste Möglichkeit, um die Implementierung zu imitieren:</span><span class="sxs-lookup"><span data-stu-id="78212-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="78212-110">Rückgabewert von Aufrufen der `Request` Methode für die `IXCLRDataModule*` Parameter mit den folgenden Parametern: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="78212-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>


## <a name="requirements"></a><span data-ttu-id="78212-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78212-111">Requirements</span></span>

<span data-ttu-id="78212-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78212-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="78212-113">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="78212-113">**Header:** None</span></span>     
<span data-ttu-id="78212-114">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="78212-114">**Library:** None</span></span>  
<span data-ttu-id="78212-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78212-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="78212-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78212-116">See Also</span></span>

- [<span data-ttu-id="78212-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="78212-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="78212-118">DacpGetModuleAddress-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78212-118">DacpGetModuleAddress Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md)
