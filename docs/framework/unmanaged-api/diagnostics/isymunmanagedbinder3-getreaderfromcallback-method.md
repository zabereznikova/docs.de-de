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
ms.openlocfilehash: 4a23e9aa259f430c0d0579657952fc6aba4c307c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441655"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="d14fc-102">ISymUnmanagedBinder3::GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="d14fc-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="d14fc-103">Ermöglicht dem Benutzer das implementieren oder Bereitstellen von per Callback entweder `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` , um die debugverzeichnisinformationen aus dem Arbeitsspeicher abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d14fc-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d14fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d14fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d14fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d14fc-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="d14fc-106">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="d14fc-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d14fc-107">in Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="d14fc-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="d14fc-108">in Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="d14fc-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="d14fc-109">in Ein Wert der [corsymsearchpolicyattribute](corsymsearchpolicyattributes-enumeration.md) -Enumeration, der die Richtlinie angibt, die bei einer Suche nach einem Symbol Leser verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d14fc-109">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="d14fc-110">in Ein Zeiger auf die Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="d14fc-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d14fc-111">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d14fc-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d14fc-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d14fc-112">Return Value</span></span>  
 <span data-ttu-id="d14fc-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d14fc-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d14fc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d14fc-114">Requirements</span></span>  
 <span data-ttu-id="d14fc-115">**Header:** Corsym. idl</span><span class="sxs-lookup"><span data-stu-id="d14fc-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14fc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d14fc-116">See also</span></span>

- [<span data-ttu-id="d14fc-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d14fc-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
