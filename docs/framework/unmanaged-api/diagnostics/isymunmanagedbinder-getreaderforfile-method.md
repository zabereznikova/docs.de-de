---
title: ISymUnmanagedBinder::GetReaderForFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderForFile
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 856f7eb506f77181d41ebd10148f321197ebfda3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="441ed-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="441ed-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="441ed-103">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Struktur, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="441ed-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="441ed-104">Diese Methode wird die Programmdatenbankdatei (PDB) geöffnet, nur dann, wenn es neben der ausführbaren Datei ist.</span><span class="sxs-lookup"><span data-stu-id="441ed-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="441ed-105">Aus Sicherheitsgründen wurde diese Änderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="441ed-105">This change has been made for security purposes.</span></span> <span data-ttu-id="441ed-106">Wenn Sie eine ausführliche Suche für die PDB-Datei, verwenden die [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="441ed-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="441ed-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="441ed-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="441ed-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="441ed-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="441ed-109">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="441ed-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="441ed-110">[in] Ein Zeiger auf den Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="441ed-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="441ed-111">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="441ed-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="441ed-112">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="441ed-112">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="441ed-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="441ed-113">Return Value</span></span>  
 <span data-ttu-id="441ed-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="441ed-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="441ed-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="441ed-115">Requirements</span></span>  
 <span data-ttu-id="441ed-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="441ed-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441ed-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="441ed-117">See Also</span></span>  
 [<span data-ttu-id="441ed-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="441ed-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="441ed-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="441ed-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
