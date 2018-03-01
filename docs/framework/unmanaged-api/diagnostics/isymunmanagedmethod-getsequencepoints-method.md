---
title: ISymUnmanagedMethod::GetSequencePoints-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 071cbb6c33b56cb4fb409ab634a89f589db5bab8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="943c9-102">ISymUnmanagedMethod::GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="943c9-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="943c9-103">Ruft die Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="943c9-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="943c9-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="943c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="943c9-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="943c9-106">[in] Ein `ULONG32` , empfängt die Größe der `offsets`, `documents`, `lines`, `columns`, `endLines`, und `endColumns` Arrays.</span><span class="sxs-lookup"><span data-stu-id="943c9-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="943c9-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Länge des Puffers benötigt, um die Sequenzpunkte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="943c9-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="943c9-108">[in] Ein Array zum Speichern der Microsoft intermediate Language (MSIL)-vom Anfang der Methode für die Sequenzpunkte Offsets.</span><span class="sxs-lookup"><span data-stu-id="943c9-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="943c9-109">[in] Ein Array zum Speichern der Dokumente, in denen sich die Sequenzpunkte befinden.</span><span class="sxs-lookup"><span data-stu-id="943c9-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="943c9-110">[in] Ein Array, in dem die Zeilen in den Dokumenten gespeichert, in denen sich die Sequenzpunkte befinden.</span><span class="sxs-lookup"><span data-stu-id="943c9-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="943c9-111">[in] Ein Array zum Speichern der Spalten in den Dokumenten, in denen sich die Sequenzpunkte befinden.</span><span class="sxs-lookup"><span data-stu-id="943c9-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="943c9-112">[in] Das Array von Zeilen in den Dokumenten, in denen die Sequenzpunkte enden.</span><span class="sxs-lookup"><span data-stu-id="943c9-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="943c9-113">[in] Das Array von Spalten in den Dokumenten, in denen die Sequenzpunkte enden.</span><span class="sxs-lookup"><span data-stu-id="943c9-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="943c9-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="943c9-114">Return Value</span></span>  
 <span data-ttu-id="943c9-115">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="943c9-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943c9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="943c9-116">Requirements</span></span>  
 <span data-ttu-id="943c9-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="943c9-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943c9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="943c9-118">See Also</span></span>  
 [<span data-ttu-id="943c9-119">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="943c9-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
