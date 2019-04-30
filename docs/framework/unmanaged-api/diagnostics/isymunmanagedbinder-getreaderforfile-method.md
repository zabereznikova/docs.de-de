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
ms.openlocfilehash: 0414cadca910f3290f96a841e3f807f0de469606
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940087"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="7b82a-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7b82a-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="7b82a-103">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle, die die Debugsymbole, die dem Modul zugeordneten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="7b82a-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="7b82a-104">Diese Methode öffnet die Programmdatenbankdatei (PDB), nur dann, wenn es neben der ausführbaren Datei ist.</span><span class="sxs-lookup"><span data-stu-id="7b82a-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="7b82a-105">Aus Sicherheitsgründen wurde diese Änderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="7b82a-105">This change has been made for security purposes.</span></span> <span data-ttu-id="7b82a-106">Wenn Sie eine ausführliche Suche für die PDB-Datei benötigen, verwenden Sie die [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7b82a-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b82a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b82a-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b82a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b82a-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7b82a-109">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7b82a-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="7b82a-110">[in] Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="7b82a-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7b82a-111">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="7b82a-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7b82a-112">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7b82a-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b82a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b82a-113">Return Value</span></span>  
 <span data-ttu-id="7b82a-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7b82a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b82a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b82a-115">Requirements</span></span>  
 <span data-ttu-id="7b82a-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b82a-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b82a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b82a-117">See also</span></span>

- [<span data-ttu-id="7b82a-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b82a-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="7b82a-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="7b82a-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
