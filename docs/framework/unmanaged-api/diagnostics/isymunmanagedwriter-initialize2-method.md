---
title: ISymUnmanagedWriter::Initialize2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 015c7d43a856990251b3e67febe685759cc4e5fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="538d8-102">ISymUnmanagedWriter::Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="538d8-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="538d8-103">Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, den die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="538d8-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="538d8-104">Dieser Methode können auch den endgültigen Speicherort der Programmdatenbankdatei (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="538d8-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="538d8-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="538d8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="538d8-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="538d8-107">[in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="538d8-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="538d8-108">[in] Ein Zeiger auf eine `WCHAR` , enthält der Dateiname, der in die die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="538d8-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="538d8-109">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="538d8-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="538d8-110">[in] Wenn angegeben, gibt der Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> anstatt in die angegebene Datei der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="538d8-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="538d8-111">Der Parameter `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="538d8-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="538d8-112">[in] `true` ist dies eine vollständige Neuerstellung; `false` ist dies eine inkrementelle Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="538d8-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="538d8-113">[in] Ein Zeiger auf eine `WCHAR` also die Pfadzeichenfolge an den endgültigen Speicherort der PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="538d8-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="538d8-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="538d8-114">Return Value</span></span>  
 <span data-ttu-id="538d8-115">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="538d8-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="538d8-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="538d8-116">Requirements</span></span>  
 <span data-ttu-id="538d8-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="538d8-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538d8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="538d8-118">See Also</span></span>  
 [<span data-ttu-id="538d8-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="538d8-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="538d8-120">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="538d8-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
