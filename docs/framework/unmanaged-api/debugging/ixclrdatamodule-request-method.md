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
ms.openlocfilehash: a02a60668ae6caaad1940395822758331b93f550
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119794"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="e2c98-102">IXCLRDataModule::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="e2c98-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="e2c98-103">Anforderungen zum Auffüllen mit Daten für das Modul des angegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="e2c98-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e2c98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2c98-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="e2c98-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2c98-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="e2c98-106">[in] Der Anforderungstyp gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2c98-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="e2c98-107">[in] die Größe des Eingabepuffers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e2c98-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="e2c98-108">[in, size_is(inBufferSize)] Zeiger auf den Puffer für die Rohdaten in der Anforderung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2c98-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="e2c98-109">[in] Die Größe des Ausgabepuffers.</span><span class="sxs-lookup"><span data-stu-id="e2c98-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="e2c98-110">[Out, size_is(outBufferSize)] Zeiger auf den Puffer zum Speichern der Anforderungsantwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2c98-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2c98-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2c98-111">Remarks</span></span>

<span data-ttu-id="e2c98-112">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem der 36. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="e2c98-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2c98-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2c98-113">Requirements</span></span>

<span data-ttu-id="e2c98-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2c98-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e2c98-115">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e2c98-115">**Header:** None</span></span>   
<span data-ttu-id="e2c98-116">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="e2c98-116">**Library:** None</span></span>  
**<span data-ttu-id="e2c98-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e2c98-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="e2c98-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2c98-118">See also</span></span>

- [<span data-ttu-id="e2c98-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e2c98-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="e2c98-120">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2c98-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)