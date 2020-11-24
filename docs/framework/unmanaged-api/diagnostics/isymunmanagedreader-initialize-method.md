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
ms.openlocfilehash: 6193d91c8cbe0efa7cd68b97b9262acf72c9ea0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675879"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="19f44-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="19f44-102">ISymUnmanagedReader::Initialize Method</span></span>

<span data-ttu-id="19f44-103">Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="19f44-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19f44-104">Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="19f44-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f44-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19f44-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19f44-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="19f44-106">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="19f44-107">in Die metadatenimporterschnittstelle, der dieser Reader zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="19f44-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="19f44-108">in Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="19f44-108">[in] The file name of the module.</span></span> <span data-ttu-id="19f44-109">Stattdessen können Sie den- `pIStream` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="19f44-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="19f44-110">in Der zu durchsuchende Pfad.</span><span class="sxs-lookup"><span data-stu-id="19f44-110">[in] The path to search.</span></span> <span data-ttu-id="19f44-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="19f44-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="19f44-112">in Der Dateistream, der als Alternative zum filename-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19f44-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19f44-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19f44-113">Return Value</span></span>  

 <span data-ttu-id="19f44-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="19f44-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19f44-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19f44-115">Remarks</span></span>  

 <span data-ttu-id="19f44-116">Sie müssen nur einen der `filename` Parameter oder angeben `pIStream` , nicht beides.</span><span class="sxs-lookup"><span data-stu-id="19f44-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="19f44-117">Das `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="19f44-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f44-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19f44-118">Requirements</span></span>  

 <span data-ttu-id="19f44-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="19f44-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f44-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19f44-120">See also</span></span>

- [<span data-ttu-id="19f44-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19f44-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
