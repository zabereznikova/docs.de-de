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
ms.openlocfilehash: f2dceeb2f0b3aa9f3147157e77087dffbf2d5f85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939030"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="68fb8-102">ISymUnmanagedReader::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="68fb8-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="68fb8-103">Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="68fb8-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68fb8-104">Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Reader-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="68fb8-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fb8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="68fb8-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68fb8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="68fb8-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="68fb8-107">in Die metadatenimporterschnittstelle, der dieser Reader zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="68fb8-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="68fb8-108">in Der Dateiname des Moduls.</span><span class="sxs-lookup"><span data-stu-id="68fb8-108">[in] The file name of the module.</span></span> <span data-ttu-id="68fb8-109">Stattdessen können Sie den `pIStream` -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="68fb8-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="68fb8-110">in Der zu durchsuchende Pfad.</span><span class="sxs-lookup"><span data-stu-id="68fb8-110">[in] The path to search.</span></span> <span data-ttu-id="68fb8-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="68fb8-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="68fb8-112">in Der Dateistream, der als Alternative zum filename-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68fb8-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68fb8-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="68fb8-113">Return Value</span></span>  
 <span data-ttu-id="68fb8-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="68fb8-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68fb8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68fb8-115">Remarks</span></span>  
 <span data-ttu-id="68fb8-116">Sie müssen nur einen `filename` der `pIStream` Parameter oder angeben, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="68fb8-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="68fb8-117">Der Parameter `searchPath` ist optional.</span><span class="sxs-lookup"><span data-stu-id="68fb8-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68fb8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68fb8-118">Requirements</span></span>  
 <span data-ttu-id="68fb8-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68fb8-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fb8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68fb8-120">See also</span></span>

- [<span data-ttu-id="68fb8-121">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68fb8-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
