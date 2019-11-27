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
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449312"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="0a68a-102">ISymUnmanagedBinder3::GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="0a68a-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="0a68a-103">Ermöglicht es dem Benutzer, über einen Rückruf entweder eine `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` zu implementieren oder bereitzustellen, um die debugverzeichnisinformationen aus dem Arbeitsspeicher abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0a68a-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a68a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a68a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a68a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a68a-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0a68a-106">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="0a68a-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="0a68a-107">in Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="0a68a-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0a68a-108">in Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="0a68a-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="0a68a-109">in Ein Wert der [corsymsearchpolicyattribute](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) -Enumeration, der die Richtlinie angibt, die bei einer Suche nach einem Symbol Leser verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a68a-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="0a68a-110">in Ein Zeiger auf die Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="0a68a-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0a68a-111">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0a68a-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a68a-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0a68a-112">Return Value</span></span>  
 <span data-ttu-id="0a68a-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0a68a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a68a-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0a68a-114">Requirements</span></span>  
 <span data-ttu-id="0a68a-115">**Header:** Corsym. idl</span><span class="sxs-lookup"><span data-stu-id="0a68a-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a68a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a68a-116">See also</span></span>

- [<span data-ttu-id="0a68a-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a68a-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
