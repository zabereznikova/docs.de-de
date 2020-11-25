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
ms.openlocfilehash: ac895032e70cf31532ab4c73409d6d750eae65df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706995"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="29e18-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="29e18-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>

<span data-ttu-id="29e18-103">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="29e18-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="29e18-104">Diese Methode öffnet die Programm Datenbankdatei (PDB-Datei) nur dann, wenn Sie sich neben der ausführbaren Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="29e18-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="29e18-105">Diese Änderung wurde aus Sicherheitsgründen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="29e18-105">This change has been made for security purposes.</span></span> <span data-ttu-id="29e18-106">Wenn Sie eine umfassendere Suche nach der PDB-Datei benötigen, verwenden Sie die [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="29e18-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e18-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="29e18-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29e18-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="29e18-108">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="29e18-109">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="29e18-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="29e18-110">in Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="29e18-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="29e18-111">in Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="29e18-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="29e18-112">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="29e18-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29e18-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29e18-113">Return Value</span></span>  

 <span data-ttu-id="29e18-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="29e18-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29e18-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="29e18-115">Requirements</span></span>  

 <span data-ttu-id="29e18-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="29e18-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e18-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29e18-117">See also</span></span>

- [<span data-ttu-id="29e18-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29e18-118">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="29e18-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="29e18-119">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
