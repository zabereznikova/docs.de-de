---
title: ISymUnmanagedMethod::GetSequencePoints-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448876"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="1670b-102">ISymUnmanagedMethod::GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="1670b-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="1670b-103">Ruft alle Sequenz Punkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="1670b-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1670b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1670b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="1670b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1670b-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="1670b-106">in Eine `ULONG32`, die die Größe der Arrays `offsets`, `documents`, `lines`, `columns`, `endLines`und `endColumns` empfängt.</span><span class="sxs-lookup"><span data-stu-id="1670b-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="1670b-107">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Länge des Puffers empfängt, der zum enthalten der Sequenz Punkte benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1670b-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="1670b-108">in Ein Array, in dem die MSIL-Offsets (Microsoft Intermediate Language) vom Anfang der Methode für die Sequenz Punkte gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1670b-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="1670b-109">in Ein Array, in dem die Dokumente gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.</span><span class="sxs-lookup"><span data-stu-id="1670b-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="1670b-110">in Ein Array, in dem die Zeilen in den Dokumenten gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.</span><span class="sxs-lookup"><span data-stu-id="1670b-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="1670b-111">in Ein Array, in dem die Spalten in den Dokumenten gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.</span><span class="sxs-lookup"><span data-stu-id="1670b-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="1670b-112">in Das Array von Zeilen in den Dokumenten, in denen die Sequenz Punkte enden.</span><span class="sxs-lookup"><span data-stu-id="1670b-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="1670b-113">in Das Array von Spalten in den Dokumenten, in denen die Sequenz Punkte enden.</span><span class="sxs-lookup"><span data-stu-id="1670b-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1670b-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1670b-114">Return Value</span></span>  
 <span data-ttu-id="1670b-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1670b-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1670b-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1670b-116">Requirements</span></span>  
 <span data-ttu-id="1670b-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1670b-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1670b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1670b-118">See also</span></span>

- [<span data-ttu-id="1670b-119">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1670b-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
