---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c0ff6d48bc749b1d8850f94fb1dc1adf3de8e37
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="ccc8e-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="ccc8e-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="ccc8e-103">Ermöglicht es einen Compiler, um Funktionen, die aus dem Programm Programmdatenbankdatei (PDB)-Stream nicht geändert wurden zu unterdrücken, sofern die Daten die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="ccc8e-104">Die richtige Zeileninformationen kann mit den alten PDB-Zeileninformationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc8e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccc8e-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccc8e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccc8e-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="ccc8e-107">[in] Ein Zeiger auf eine <xref:IStream> , die die Zeileninformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-107">[in] A pointer to an <xref:IStream> that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="ccc8e-108">[in] Ein Zeiger auf eine [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) -Struktur, die die Zeilen enthält, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="ccc8e-109">[in] Ein `ULONG` stellt die Anzahl von Zeilen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccc8e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ccc8e-110">Return Value</span></span>  
 <span data-ttu-id="ccc8e-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ccc8e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc8e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccc8e-112">Requirements</span></span>  
 <span data-ttu-id="ccc8e-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ccc8e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc8e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccc8e-114">See Also</span></span>  
 [<span data-ttu-id="ccc8e-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccc8e-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
