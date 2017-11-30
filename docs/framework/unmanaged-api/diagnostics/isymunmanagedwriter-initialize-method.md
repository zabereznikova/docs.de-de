---
title: ISymUnmanagedWriter::Initialize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="685b6-102">ISymUnmanagedWriter::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="685b6-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="685b6-103">Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, den die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="685b6-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="685b6-104">Diese Methode kann nur einmal aufgerufen werden, und es muss vor anderen Writermethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="685b6-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="685b6-105">Einige Writer erfordern einen Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="685b6-105">Some writers may require a file name.</span></span> <span data-ttu-id="685b6-106">Allerdings können Sie immer einen Dateinamen an diese Methode ohne negative Auswirkung auf Writer übergeben, die nicht den Dateinamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="685b6-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685b6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="685b6-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="685b6-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="685b6-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="685b6-109">[in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="685b6-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="685b6-110">[in] Der Dateiname, der die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="685b6-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="685b6-111">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="685b6-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="685b6-112">[in] Wenn angegeben, die Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> anstatt in die angegebene Datei der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="685b6-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="685b6-113">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="685b6-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="685b6-114">[in] `true` ist dies eine vollständige Neuerstellung; `false` ist dies eine inkrementelle Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="685b6-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="685b6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="685b6-115">Return Value</span></span>  
 <span data-ttu-id="685b6-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="685b6-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685b6-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="685b6-117">Requirements</span></span>  
 <span data-ttu-id="685b6-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="685b6-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685b6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="685b6-119">See Also</span></span>  
 [<span data-ttu-id="685b6-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="685b6-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="685b6-121">Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="685b6-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
