---
title: ISymUnmanagedBinder3::GetReaderFromCallback-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5767b60fa992b49fdc2a60feb243a26c0e2ea1ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534548"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="850aa-102">ISymUnmanagedBinder3::GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="850aa-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="850aa-103">Ermöglicht dem Benutzer zu implementieren, oder geben Sie entweder über den Rückruf ein `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="850aa-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="850aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="850aa-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="850aa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="850aa-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="850aa-106">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850aa-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="850aa-107">[in] Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="850aa-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="850aa-108">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="850aa-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="850aa-109">[in] Der Wert der [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) Enumeration, die die Richtlinie verwendet werden, wenn eine Suche für einen Symbolreader angibt.</span><span class="sxs-lookup"><span data-stu-id="850aa-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="850aa-110">[in] Ein Zeiger auf die Callback-Funktion.</span><span class="sxs-lookup"><span data-stu-id="850aa-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="850aa-111">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850aa-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="850aa-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="850aa-112">Return Value</span></span>  
 <span data-ttu-id="850aa-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="850aa-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="850aa-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="850aa-114">Requirements</span></span>  
 <span data-ttu-id="850aa-115">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="850aa-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850aa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="850aa-116">See also</span></span>
- [<span data-ttu-id="850aa-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="850aa-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
