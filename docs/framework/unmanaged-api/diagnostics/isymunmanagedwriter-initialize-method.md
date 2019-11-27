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
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="b6b60-102">ISymUnmanagedWriter::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b60-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="b6b60-103">Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b6b60-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="b6b60-104">Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Writer-Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b6b60-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="b6b60-105">Einige Writer benötigen möglicherweise einen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="b6b60-105">Some writers may require a file name.</span></span> <span data-ttu-id="b6b60-106">Allerdings können Sie immer einen Dateinamen an diese Methode übergeben, ohne dass Sie negative Auswirkungen auf Writer haben, die den Dateinamen nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6b60-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b60-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6b60-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6b60-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6b60-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="b6b60-109">in Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b6b60-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="b6b60-110">in Der Name der Datei, in die die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b6b60-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="b6b60-111">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b6b60-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="b6b60-112">in Wenn angegeben, gibt der Symbolwriter die Symbole in die angegebene <xref:System.Runtime.InteropServices.ComTypes.IStream> und nicht in die Datei aus, die im `filename`-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b6b60-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="b6b60-113">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="b6b60-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="b6b60-114">[in] `true`, wenn dies eine vollständige Neuerstellung ist. `false` wenn dies eine inkrementelle Kompilierung ist.</span><span class="sxs-lookup"><span data-stu-id="b6b60-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6b60-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b6b60-115">Return Value</span></span>  
 <span data-ttu-id="b6b60-116">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b6b60-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b60-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b6b60-117">Requirements</span></span>  
 <span data-ttu-id="b6b60-118">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b6b60-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b60-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6b60-119">See also</span></span>

- [<span data-ttu-id="b6b60-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6b60-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b6b60-121">Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b60-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
