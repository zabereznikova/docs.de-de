---
title: ISymUnmanagedWriter::Initialize2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f65262a9b9850d93e934a77f154bb625a55e1e82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514243"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="845e0-102">ISymUnmanagedWriter::Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="845e0-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="845e0-103">Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="845e0-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="845e0-104">Mit dieser Methode können auch den endgültigen Speicherort, der die Programmdatenbankdatei (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="845e0-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="845e0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="845e0-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="845e0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="845e0-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="845e0-107">[in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="845e0-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="845e0-108">[in] Ein Zeiger auf eine `WCHAR` , enthält der Dateiname, der die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="845e0-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="845e0-109">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="845e0-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="845e0-110">[in] Wenn angegeben, gibt der Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> statt in der Datei angegeben, der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="845e0-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="845e0-111">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="845e0-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="845e0-112">[in] `true` ist dies eine vollständige Neuerstellung `false` ist dies eine inkrementelle Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="845e0-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="845e0-113">[in] Ein Zeiger auf eine `WCHAR` d. h. die Pfadzeichenfolge, um den endgültigen Speicherort der PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="845e0-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="845e0-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="845e0-114">Return Value</span></span>  
 <span data-ttu-id="845e0-115">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="845e0-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="845e0-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="845e0-116">Requirements</span></span>  
 <span data-ttu-id="845e0-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="845e0-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845e0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="845e0-118">See also</span></span>
- [<span data-ttu-id="845e0-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="845e0-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="845e0-120">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="845e0-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
