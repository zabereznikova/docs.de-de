---
title: ISymUnmanagedBinder2::GetReaderForFile2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fed289b2776e8ac4a12969060cd16c6163ebed2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091966"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="e0663-102">ISymUnmanagedBinder2::GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="e0663-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="e0663-103">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle, die die Debugsymbole, die dem Modul zugeordneten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="e0663-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="e0663-104">Diese Methode bietet eine ausführliche Suche für die Programmdatenbankdatei (PDB) als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e0663-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0663-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0663-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0663-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0663-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e0663-107">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e0663-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="e0663-108">[in] Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="e0663-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e0663-109">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="e0663-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="e0663-110">[in] Der Wert der [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) Enumeration, die die Richtlinie verwendet werden, wenn eine Suche für einen Symbolreader angibt.</span><span class="sxs-lookup"><span data-stu-id="e0663-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e0663-111">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e0663-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0663-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e0663-112">Return Value</span></span>  
 <span data-ttu-id="e0663-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e0663-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0663-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0663-114">Requirements</span></span>  
 <span data-ttu-id="e0663-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0663-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0663-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0663-116">Remarks</span></span>  
 <span data-ttu-id="e0663-117">Diese Version der Methode kann die PDB-Datei, in anderen Bereichen als rechts neben dem Modul suchen.</span><span class="sxs-lookup"><span data-stu-id="e0663-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="e0663-118">Die Richtlinie für die Suche kann gesteuert werden, durch Kombinieren von [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="e0663-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="e0663-119">Z. B. `AllowReferencePathAccess | AllowSymbolServerAccess` sucht die PDB-Datei neben der ausführbaren Datei, und klicken Sie auf einem Symbolserver, jedoch keine Abfragen die Registrierung oder verwenden Sie den Pfad in der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="e0663-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="e0663-120">Wenn die `searchPath` -Parameter bereitgestellt wird, werden immer diese Verzeichnisse durchsucht.</span><span class="sxs-lookup"><span data-stu-id="e0663-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0663-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0663-121">See also</span></span>

- [<span data-ttu-id="e0663-122">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0663-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="e0663-123">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="e0663-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
