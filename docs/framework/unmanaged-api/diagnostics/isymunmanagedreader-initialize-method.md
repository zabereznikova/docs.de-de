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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615474"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="a67a9-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="a67a9-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="a67a9-103">Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="a67a9-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a67a9-104">Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a67a9-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a67a9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a67a9-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a67a9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a67a9-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="a67a9-107">in Die metadatenimporterschnittstelle, der dieser Reader zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="a67a9-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="a67a9-108">in Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="a67a9-108">[in] The file name of the module.</span></span> <span data-ttu-id="a67a9-109">Stattdessen können Sie den- `pIStream` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a67a9-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="a67a9-110">in Der zu durchsuchende Pfad.</span><span class="sxs-lookup"><span data-stu-id="a67a9-110">[in] The path to search.</span></span> <span data-ttu-id="a67a9-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="a67a9-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="a67a9-112">in Der Dateistream, der als Alternative zum filename-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a67a9-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a67a9-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a67a9-113">Return Value</span></span>  
 <span data-ttu-id="a67a9-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a67a9-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a67a9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a67a9-115">Remarks</span></span>  
 <span data-ttu-id="a67a9-116">Sie müssen nur einen der `filename` Parameter oder angeben `pIStream` , nicht beides.</span><span class="sxs-lookup"><span data-stu-id="a67a9-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="a67a9-117">Das `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="a67a9-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a67a9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a67a9-118">Requirements</span></span>  
 <span data-ttu-id="a67a9-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a67a9-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a67a9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a67a9-120">See also</span></span>

- [<span data-ttu-id="a67a9-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a67a9-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
