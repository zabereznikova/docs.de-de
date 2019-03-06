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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a4bcc4e6994f06fabf69e5548ad6922343b7dd5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479791"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="d87d2-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="d87d2-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="d87d2-103">Ermöglicht es einen Compiler, um Funktionen, die nicht aus dem Stream Programm Programmdatenbankdatei (PDB) geändert wurden zu unterdrücken, sofern die Zeileninformationen die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d87d2-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="d87d2-104">Die richtige Zeileninformationen kann mit der alten Zeileninformationen für die PDB-Datei und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="d87d2-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d87d2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d87d2-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d87d2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d87d2-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="d87d2-107">[in] Ein Zeiger auf ein [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , das die Zeileninformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d87d2-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="d87d2-108">[in] Ein Zeiger auf eine [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) Struktur, die die Zeilen enthält, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="d87d2-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="d87d2-109">[in] Ein `ULONG` , die die Anzahl der Zeilen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="d87d2-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d87d2-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d87d2-110">Return Value</span></span>  
 <span data-ttu-id="d87d2-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d87d2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d87d2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d87d2-112">Requirements</span></span>  
 <span data-ttu-id="d87d2-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d87d2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87d2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d87d2-114">See also</span></span>
- [<span data-ttu-id="d87d2-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d87d2-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
