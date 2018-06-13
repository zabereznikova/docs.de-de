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
ms.openlocfilehash: 5f44d50f6736e0698fd876eedab78dbf41434af4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426315"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="10975-102">ISymUnmanagedBinder3::GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="10975-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="10975-103">Ermöglicht es dem Benutzer zu implementieren, oder geben Sie entweder über Rückruf eine `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="10975-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10975-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10975-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10975-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10975-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="10975-106">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="10975-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="10975-107">[in] Ein Zeiger auf den Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="10975-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="10975-108">[in] Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="10975-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="10975-109">[in] Der Wert der [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) Enumeration, die die Richtlinie verwendet werden, wenn eine Suche für einen Symbolreader angibt.</span><span class="sxs-lookup"><span data-stu-id="10975-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="10975-110">[in] Ein Zeiger auf die Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="10975-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="10975-111">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="10975-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10975-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10975-112">Return Value</span></span>  
 <span data-ttu-id="10975-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="10975-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10975-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10975-114">Requirements</span></span>  
 <span data-ttu-id="10975-115">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="10975-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10975-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10975-116">See Also</span></span>  
 [<span data-ttu-id="10975-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10975-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
