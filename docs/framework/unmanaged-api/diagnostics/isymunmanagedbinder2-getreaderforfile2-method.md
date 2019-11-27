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
ms.openlocfilehash: 756ba2e71ca2e3e817a0a8b89165bb807368c1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449331"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="7f71d-102">ISymUnmanagedBinder2::GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="7f71d-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="7f71d-103">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="7f71d-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="7f71d-104">Diese Methode bietet eine ausführlichere Suche nach der Programm Datenbankdatei (PDB) als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="7f71d-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f71d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f71d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f71d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f71d-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7f71d-107">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="7f71d-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="7f71d-108">in Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="7f71d-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7f71d-109">in Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="7f71d-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="7f71d-110">in Ein Wert der [corsymsearchpolicyattribute](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) -Enumeration, der die Richtlinie angibt, die bei einer Suche nach einem Symbol Leser verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f71d-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7f71d-111">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7f71d-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f71d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7f71d-112">Return Value</span></span>  
 <span data-ttu-id="7f71d-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7f71d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f71d-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7f71d-114">Requirements</span></span>  
 <span data-ttu-id="7f71d-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="7f71d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f71d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f71d-116">Remarks</span></span>  
 <span data-ttu-id="7f71d-117">Diese Version der-Methode kann nach der PDB-Datei in anderen Bereichen als rechts neben dem-Modul suchen.</span><span class="sxs-lookup"><span data-stu-id="7f71d-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="7f71d-118">Die Such Richtlinie kann durch Kombinieren von [corsymsearchpolicyattribute](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="7f71d-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="7f71d-119">`AllowReferencePathAccess | AllowSymbolServerAccess` sucht beispielsweise nach der PDB neben der ausführbaren Datei und auf einem Symbol Server, fragt jedoch nicht die Registrierung ab oder verwendet den Pfad in der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="7f71d-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="7f71d-120">Wenn der `searchPath`-Parameter bereitgestellt wird, werden diese Verzeichnisse immer durchsucht.</span><span class="sxs-lookup"><span data-stu-id="7f71d-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f71d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f71d-121">See also</span></span>

- [<span data-ttu-id="7f71d-122">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f71d-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="7f71d-123">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7f71d-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
