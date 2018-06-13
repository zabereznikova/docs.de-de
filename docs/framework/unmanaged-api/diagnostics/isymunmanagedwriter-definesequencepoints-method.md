---
title: ISymUnmanagedWriter::DefineSequencePoints-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dc87b201638bab974c59722a69300977b14cf08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426935"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="5c57a-102">ISymUnmanagedWriter::DefineSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="5c57a-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="5c57a-103">Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="5c57a-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="5c57a-104">Jede Anfangszeile und die Anfangsspalte definieren den Start einer Anweisung innerhalb einer Methode.</span><span class="sxs-lookup"><span data-stu-id="5c57a-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="5c57a-105">Jede Zeile endet und Endspalte definieren eine Anweisung innerhalb einer Methode.</span><span class="sxs-lookup"><span data-stu-id="5c57a-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="5c57a-106">Die Arrays müssen in aufsteigender Reihenfolge der Offsets sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="5c57a-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="5c57a-107">Der Offset wird immer vom Anfang der Methode in Byte gemessen.</span><span class="sxs-lookup"><span data-stu-id="5c57a-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c57a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c57a-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c57a-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c57a-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="5c57a-110">[in] Das Dokumentobjekt, für das die Sequenzpunkte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5c57a-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="5c57a-111">[in] Ein `ULONG32` an, die die Größe der einzelnen gibt die `offsets`, `lines`, `columns`, `endLines`, und `endColumns` Puffer.</span><span class="sxs-lookup"><span data-stu-id="5c57a-111">[in] A `ULONG32` that that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="5c57a-112">[in] Der Offset der Sequenzpunkte gemessen vom Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="5c57a-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="5c57a-113">[in] Die Anfangszeilennummern der Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="5c57a-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="5c57a-114">[in] Die ersten Spaltennummern der Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="5c57a-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="5c57a-115">[in] Die Endzeilennummern der Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="5c57a-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="5c57a-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c57a-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="5c57a-117">[in] Die Endadresse Spaltennummern der Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="5c57a-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="5c57a-118">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c57a-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c57a-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5c57a-119">Return Value</span></span>  
 <span data-ttu-id="5c57a-120">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5c57a-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c57a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c57a-121">Requirements</span></span>  
 <span data-ttu-id="5c57a-122">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5c57a-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c57a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c57a-123">See Also</span></span>  
 [<span data-ttu-id="5c57a-124">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c57a-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
