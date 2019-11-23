---
title: ISymUnmanagedWriter::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427978"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="6f337-102">ISymUnmanagedWriter::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="6f337-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="6f337-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span><span class="sxs-lookup"><span data-stu-id="6f337-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="6f337-104">This method can be called only once, and it must be called before any other writer methods.</span><span class="sxs-lookup"><span data-stu-id="6f337-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="6f337-105">Some writers may require a file name.</span><span class="sxs-lookup"><span data-stu-id="6f337-105">Some writers may require a file name.</span></span> <span data-ttu-id="6f337-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span><span class="sxs-lookup"><span data-stu-id="6f337-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f337-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f337-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f337-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f337-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="6f337-109">[in] A pointer to the metadata emitter interface.</span><span class="sxs-lookup"><span data-stu-id="6f337-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="6f337-110">[in] The file name to which the debugging symbols are written.</span><span class="sxs-lookup"><span data-stu-id="6f337-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="6f337-111">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6f337-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="6f337-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span><span class="sxs-lookup"><span data-stu-id="6f337-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="6f337-113">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="6f337-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="6f337-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span><span class="sxs-lookup"><span data-stu-id="6f337-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f337-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f337-115">Return Value</span></span>  
 <span data-ttu-id="6f337-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="6f337-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f337-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f337-117">Requirements</span></span>  
 <span data-ttu-id="6f337-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6f337-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f337-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f337-119">See also</span></span>

- [<span data-ttu-id="6f337-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f337-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6f337-121">Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="6f337-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
