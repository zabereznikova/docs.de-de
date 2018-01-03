---
title: ISymUnmanagedReader::Initialize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="5de67-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="5de67-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="5de67-103">Initialisiert den Symbolreader mit der Schnittstelle für die Metadaten, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.</span><span class="sxs-lookup"><span data-stu-id="5de67-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5de67-104">Diese Methode kann nur einmal aufgerufen werden und muss vor anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5de67-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de67-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5de67-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5de67-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5de67-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="5de67-107">[in] Die Metadaten-Importer-Tool-Schnittstelle mit der dieser Reader zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5de67-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="5de67-108">[in] Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="5de67-108">[in] The file name of the module.</span></span> <span data-ttu-id="5de67-109">Sie können die `pIStream` Parameter stattdessen.</span><span class="sxs-lookup"><span data-stu-id="5de67-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="5de67-110">[in] Der Pfad zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5de67-110">[in] The path to search.</span></span> <span data-ttu-id="5de67-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="5de67-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="5de67-112">[in] Die Dateidatenstrom, der als Alternative zum Filename-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de67-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5de67-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5de67-113">Return Value</span></span>  
 <span data-ttu-id="5de67-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5de67-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de67-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5de67-115">Remarks</span></span>  
 <span data-ttu-id="5de67-116">Müssen Sie nur einen angeben der `filename` oder `pIStream` Parameter, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="5de67-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="5de67-117">Der Parameter `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="5de67-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de67-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5de67-118">Requirements</span></span>  
 <span data-ttu-id="5de67-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5de67-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de67-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5de67-120">See Also</span></span>  
 [<span data-ttu-id="5de67-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5de67-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
