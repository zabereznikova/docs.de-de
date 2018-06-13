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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44046560f4f788c4a7d695ff18c9c01740fea35a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428034"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="30024-102">ISymUnmanagedWriter::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="30024-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="30024-103">Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, den die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="30024-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="30024-104">Diese Methode kann nur einmal aufgerufen werden, und es muss vor anderen Writermethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30024-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="30024-105">Einige Writer erfordern einen Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="30024-105">Some writers may require a file name.</span></span> <span data-ttu-id="30024-106">Allerdings können Sie immer einen Dateinamen an diese Methode ohne negative Auswirkung auf Writer übergeben, die nicht den Dateinamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="30024-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30024-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="30024-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30024-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="30024-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="30024-109">[in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="30024-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="30024-110">[in] Der Dateiname, der die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="30024-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="30024-111">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="30024-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="30024-112">[in] Wenn angegeben, die Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> anstatt in die angegebene Datei der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="30024-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="30024-113">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="30024-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="30024-114">[in] `true` ist dies eine vollständige Neuerstellung; `false` ist dies eine inkrementelle Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="30024-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30024-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30024-115">Return Value</span></span>  
 <span data-ttu-id="30024-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="30024-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30024-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30024-117">Requirements</span></span>  
 <span data-ttu-id="30024-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30024-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30024-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30024-119">See Also</span></span>  
 [<span data-ttu-id="30024-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30024-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="30024-121">Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="30024-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
