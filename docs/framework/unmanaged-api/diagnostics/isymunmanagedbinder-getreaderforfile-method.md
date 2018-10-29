---
title: ISymUnmanagedBinder::GetReaderForFile-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df6a35dcaebc681aa5463a014d3283c81efea617
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199863"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="0e9a1-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="0e9a1-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="0e9a1-103">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle, die die Debugsymbole, die dem Modul zugeordneten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="0e9a1-104">Diese Methode öffnet die Programmdatenbankdatei (PDB), nur dann, wenn es neben der ausführbaren Datei ist.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="0e9a1-105">Aus Sicherheitsgründen wurde diese Änderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-105">This change has been made for security purposes.</span></span> <span data-ttu-id="0e9a1-106">Wenn Sie eine ausführliche Suche für die PDB-Datei benötigen, verwenden Sie die [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9a1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e9a1-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e9a1-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e9a1-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0e9a1-109">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="0e9a1-110">[in] Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0e9a1-111">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0e9a1-112">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e9a1-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e9a1-113">Return Value</span></span>  
 <span data-ttu-id="0e9a1-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0e9a1-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e9a1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e9a1-115">Requirements</span></span>  
 <span data-ttu-id="0e9a1-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e9a1-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9a1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e9a1-117">See Also</span></span>  
 [<span data-ttu-id="0e9a1-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e9a1-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="0e9a1-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="0e9a1-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
