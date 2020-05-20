---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: f363bed8e7002bf898755b434c919f8722dea3fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614499"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="1f9da-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="1f9da-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="1f9da-103">Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1f9da-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="1f9da-104">Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="1f9da-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f9da-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f9da-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f9da-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f9da-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="1f9da-107">in Ein Zeiger auf einen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , der die Zeilen Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="1f9da-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="1f9da-108">in Ein Zeiger auf eine [SYMLINEDELTA](symlinedelta-structure.md) -Struktur, die die geänderten Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="1f9da-108">[in] A pointer to a [SYMLINEDELTA](symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="1f9da-109">in Eine `ULONG` , die die Anzahl der geänderten Zeilen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f9da-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f9da-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1f9da-110">Return Value</span></span>  
 <span data-ttu-id="1f9da-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1f9da-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f9da-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f9da-112">Requirements</span></span>  
 <span data-ttu-id="1f9da-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1f9da-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9da-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f9da-114">See also</span></span>

- [<span data-ttu-id="1f9da-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f9da-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
