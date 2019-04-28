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
ms.openlocfilehash: 417cf623948d16147f9a1242d714f4df1311a314
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700942"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="ae911-102">ISymUnmanagedWriter::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="ae911-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="ae911-103">Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ae911-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="ae911-104">Diese Methode kann nur einmal aufgerufen werden, und muss vor jedem anderen Writermethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ae911-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="ae911-105">Einige Writer erfordern einen Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="ae911-105">Some writers may require a file name.</span></span> <span data-ttu-id="ae911-106">Allerdings können Sie immer einen Dateinamen für diese Methode ohne negative Auswirkung auf Writer übergeben, die nicht den Dateinamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae911-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae911-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae911-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae911-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae911-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="ae911-109">[in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ae911-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="ae911-110">[in] Der Dateiname, der die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ae911-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="ae911-111">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ae911-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ae911-112">[in] Wenn angegeben, gibt der Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> statt in der Datei im angegebenen die `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="ae911-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="ae911-113">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="ae911-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="ae911-114">[in] `true` ist dies eine vollständige Neuerstellung `false` ist dies eine inkrementelle Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="ae911-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae911-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ae911-115">Return Value</span></span>  
 <span data-ttu-id="ae911-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ae911-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae911-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae911-117">Requirements</span></span>  
 <span data-ttu-id="ae911-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae911-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae911-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae911-119">See also</span></span>

- [<span data-ttu-id="ae911-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae911-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ae911-121">Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="ae911-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
