---
title: ISymUnmanagedReader::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d141d23f02b2abc92e3d4455aebe1a4057b6bb85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426472"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="5aecd-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="5aecd-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="5aecd-103">Initialisiert den Symbolreader mit der Schnittstelle für die Metadaten, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.</span><span class="sxs-lookup"><span data-stu-id="5aecd-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aecd-104">Diese Methode kann nur einmal aufgerufen werden und muss vor anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5aecd-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aecd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5aecd-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5aecd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5aecd-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="5aecd-107">[in] Die Metadaten-Importer-Tool-Schnittstelle mit der dieser Reader zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5aecd-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="5aecd-108">[in] Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="5aecd-108">[in] The file name of the module.</span></span> <span data-ttu-id="5aecd-109">Sie können die `pIStream` Parameter stattdessen.</span><span class="sxs-lookup"><span data-stu-id="5aecd-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="5aecd-110">[in] Der Pfad zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5aecd-110">[in] The path to search.</span></span> <span data-ttu-id="5aecd-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="5aecd-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="5aecd-112">[in] Die Dateidatenstrom, der als Alternative zum Filename-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5aecd-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5aecd-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5aecd-113">Return Value</span></span>  
 <span data-ttu-id="5aecd-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5aecd-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aecd-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5aecd-115">Remarks</span></span>  
 <span data-ttu-id="5aecd-116">Müssen Sie nur einen angeben der `filename` oder `pIStream` Parameter, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="5aecd-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="5aecd-117">Der Parameter `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="5aecd-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aecd-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5aecd-118">Requirements</span></span>  
 <span data-ttu-id="5aecd-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5aecd-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aecd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aecd-120">See Also</span></span>  
 [<span data-ttu-id="5aecd-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aecd-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
