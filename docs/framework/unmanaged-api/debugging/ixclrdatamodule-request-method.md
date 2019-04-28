---
title: IXCLRDataModule::Request-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775452"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="2b000-102">IXCLRDataModule::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="2b000-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="2b000-103">Anforderungen zum Auffüllen mit Daten für das Modul des angegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="2b000-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2b000-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b000-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="2b000-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b000-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="2b000-106">[in] Der Anforderungstyp gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b000-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="2b000-107">[in] die Größe des Eingabepuffers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2b000-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="2b000-108">[in, size_is(inBufferSize)] Zeiger auf den Puffer für die Rohdaten in der Anforderung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b000-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="2b000-109">[in] Die Größe des Ausgabepuffers.</span><span class="sxs-lookup"><span data-stu-id="2b000-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="2b000-110">[Out, size_is(outBufferSize)] Zeiger auf den Puffer zum Speichern der Anforderungsantwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b000-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b000-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b000-111">Remarks</span></span>

<span data-ttu-id="2b000-112">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem der 36. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="2b000-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b000-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b000-113">Requirements</span></span>

<span data-ttu-id="2b000-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b000-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="2b000-115">**Header:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2b000-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2b000-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b000-116">See also</span></span>

- [<span data-ttu-id="2b000-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2b000-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2b000-118">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b000-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)