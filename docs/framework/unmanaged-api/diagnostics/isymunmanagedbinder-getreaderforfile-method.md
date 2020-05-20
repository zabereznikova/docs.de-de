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
ms.openlocfilehash: c4416e8e4395c4e1967155310d12a1eb68c42d83
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441733"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="b323f-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="b323f-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="b323f-103">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="b323f-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="b323f-104">Diese Methode öffnet die Programm Datenbankdatei (PDB-Datei) nur dann, wenn Sie sich neben der ausführbaren Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="b323f-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="b323f-105">Diese Änderung wurde aus Sicherheitsgründen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="b323f-105">This change has been made for security purposes.</span></span> <span data-ttu-id="b323f-106">Wenn Sie eine umfassendere Suche nach der PDB-Datei benötigen, verwenden Sie die [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="b323f-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b323f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b323f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b323f-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b323f-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="b323f-109">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="b323f-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="b323f-110">in Ein Zeiger auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="b323f-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="b323f-111">in Ein Zeiger auf den Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="b323f-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b323f-112">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b323f-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b323f-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b323f-113">Return Value</span></span>  
 <span data-ttu-id="b323f-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b323f-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b323f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b323f-115">Requirements</span></span>  
 <span data-ttu-id="b323f-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b323f-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b323f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b323f-117">See also</span></span>

- [<span data-ttu-id="b323f-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b323f-118">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="b323f-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="b323f-119">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
