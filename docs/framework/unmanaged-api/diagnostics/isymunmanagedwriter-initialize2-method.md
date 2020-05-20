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
ms.openlocfilehash: 869d7d36ac24bfeee5b2361dd569945ad77eaf7f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610066"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="3b005-102">ISymUnmanagedWriter::Initialize2-Methode</span><span class="sxs-lookup"><span data-stu-id="3b005-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="3b005-103">Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3b005-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="3b005-104">Mit dieser Methode können Sie auch den endgültigen Speicherort der Programm Datenbankdatei (PDB-Datei) festlegen.</span><span class="sxs-lookup"><span data-stu-id="3b005-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b005-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b005-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b005-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b005-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="3b005-107">in Ein Zeiger auf die Metadatenemitter-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3b005-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="3b005-108">in Ein Zeiger auf einen-Wert `WCHAR` , der den Namen der Datei enthält, in die die Debugsymbole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3b005-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="3b005-109">Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3b005-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3b005-110">in Wenn angegeben, gibt der Symbolwriter die Symbole <xref:System.Runtime.InteropServices.ComTypes.IStream> anstelle der Datei, die im-Parameter angegeben ist, in den angegebenen aus `filename` .</span><span class="sxs-lookup"><span data-stu-id="3b005-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="3b005-111">Das `pIStream` ist optional.</span><span class="sxs-lookup"><span data-stu-id="3b005-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="3b005-112">[in] `true` , wenn es sich um eine vollständige Neuerstellung handelt. `false`Wenn dies eine inkrementelle Kompilierung ist.</span><span class="sxs-lookup"><span data-stu-id="3b005-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="3b005-113">in Ein Zeiger auf einen `WCHAR` , der die Pfad Zeichenfolge zum endgültigen Speicherort der PDB-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="3b005-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b005-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3b005-114">Return Value</span></span>  
 <span data-ttu-id="3b005-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3b005-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b005-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b005-116">Requirements</span></span>  
 <span data-ttu-id="3b005-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="3b005-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b005-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b005-118">See also</span></span>

- [<span data-ttu-id="3b005-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b005-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="3b005-120">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="3b005-120">Initialize Method</span></span>](isymunmanagedwriter-initialize-method.md)
