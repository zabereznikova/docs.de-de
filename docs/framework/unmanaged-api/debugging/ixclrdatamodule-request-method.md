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
ms.openlocfilehash: 336e47d531fc880571165cd55f117825cd1a2abb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374868"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="b82f8-102">IXCLRDataModule::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="b82f8-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="b82f8-103">Anforderungen zum Auffüllen mit Daten für das Modul des angegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="b82f8-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b82f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b82f8-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="b82f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b82f8-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="b82f8-106">[in] Der Anforderungstyp gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b82f8-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="b82f8-107">[in] die Größe des Eingabepuffers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b82f8-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="b82f8-108">[in, size_is(inBufferSize)] Zeiger auf den Puffer für die Rohdaten in der Anforderung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b82f8-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="b82f8-109">[in] Die Größe des Ausgabepuffers.</span><span class="sxs-lookup"><span data-stu-id="b82f8-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="b82f8-110">[Out, size_is(outBufferSize)] Zeiger auf den Puffer zum Speichern der Anforderungsantwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="b82f8-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="b82f8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b82f8-111">Remarks</span></span>

<span data-ttu-id="b82f8-112">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem der 36. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="b82f8-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b82f8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b82f8-113">Requirements</span></span>

<span data-ttu-id="b82f8-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b82f8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b82f8-115">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="b82f8-115">**Header:** None</span></span>   
<span data-ttu-id="b82f8-116">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="b82f8-116">**Library:** None</span></span>  
<span data-ttu-id="b82f8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b82f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b82f8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b82f8-118">See also</span></span>
- [<span data-ttu-id="b82f8-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b82f8-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="b82f8-120">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b82f8-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)