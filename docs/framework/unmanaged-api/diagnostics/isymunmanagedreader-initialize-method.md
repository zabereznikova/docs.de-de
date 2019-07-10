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
ms.openlocfilehash: 1986ed730c6f0a1ba8a2d8e3c688e6872184da9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736751"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="83d8a-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="83d8a-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="83d8a-103">Initialisiert den Symbolreader mit der Metadaten-Importer-Tool-Schnittstelle, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.</span><span class="sxs-lookup"><span data-stu-id="83d8a-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83d8a-104">Diese Methode kann nur einmal aufgerufen werden und muss vor alle anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83d8a-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d8a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83d8a-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d8a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="83d8a-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="83d8a-107">[in] Die Metadaten-Importer-Tool-Schnittstelle mit der dieser Reader zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="83d8a-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="83d8a-108">[in] Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="83d8a-108">[in] The file name of the module.</span></span> <span data-ttu-id="83d8a-109">Sie können die `pIStream` Parameter stattdessen.</span><span class="sxs-lookup"><span data-stu-id="83d8a-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="83d8a-110">[in] Der Pfad zu suchen.</span><span class="sxs-lookup"><span data-stu-id="83d8a-110">[in] The path to search.</span></span> <span data-ttu-id="83d8a-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="83d8a-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="83d8a-112">[in] Der Dateistream, der als Alternative zu den Filename-Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="83d8a-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83d8a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83d8a-113">Return Value</span></span>  
 <span data-ttu-id="83d8a-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="83d8a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83d8a-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83d8a-115">Remarks</span></span>  
 <span data-ttu-id="83d8a-116">Sie müssen nur eine der angeben der `filename` oder die `pIStream` nicht beide Parameter.</span><span class="sxs-lookup"><span data-stu-id="83d8a-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="83d8a-117">Der Parameter `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="83d8a-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d8a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83d8a-118">Requirements</span></span>  
 <span data-ttu-id="83d8a-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83d8a-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d8a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83d8a-120">See also</span></span>

- [<span data-ttu-id="83d8a-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83d8a-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
