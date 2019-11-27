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
ms.openlocfilehash: 63ba108bc234e566450bb019afc63acb4e75ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427987"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="1f915-102">ISymUnmanagedWriter::DefineSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="1f915-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="1f915-103">Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="1f915-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="1f915-104">Jede Start-und Start Spalte definiert den Anfang einer Anweisung innerhalb einer Methode.</span><span class="sxs-lookup"><span data-stu-id="1f915-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="1f915-105">Jede Endzeile und Endspalte definieren das Ende einer Anweisung innerhalb einer Methode.</span><span class="sxs-lookup"><span data-stu-id="1f915-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="1f915-106">Die Arrays sollten in aufsteigender Reihenfolge der Offsets sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f915-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="1f915-107">Der Offset wird immer vom Anfang der Methode (in Bytes) gemessen.</span><span class="sxs-lookup"><span data-stu-id="1f915-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f915-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f915-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f915-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f915-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="1f915-110">in Das Dokument Objekt, für das die Sequenz Punkte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f915-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="1f915-111">in Eine `ULONG32`, die die Größe der einzelnen `offsets`-, `lines`-, `columns`-, `endLines`-und `endColumns` Puffer angibt.</span><span class="sxs-lookup"><span data-stu-id="1f915-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="1f915-112">in Der Offset der Sequenz Punkte, gemessen ab dem Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="1f915-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="1f915-113">in Die Anfangs Zeilennummern der Sequenz Punkte.</span><span class="sxs-lookup"><span data-stu-id="1f915-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="1f915-114">in Die Nummern der Anfangs Spalten der Sequenz Punkte.</span><span class="sxs-lookup"><span data-stu-id="1f915-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="1f915-115">in Die Endzeilennummern der Sequenz Punkte.</span><span class="sxs-lookup"><span data-stu-id="1f915-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="1f915-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1f915-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="1f915-117">in Die Nummer der Endspalte der Sequenz Punkte.</span><span class="sxs-lookup"><span data-stu-id="1f915-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="1f915-118">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1f915-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f915-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1f915-119">Return Value</span></span>  
 <span data-ttu-id="1f915-120">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1f915-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f915-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1f915-121">Requirements</span></span>  
 <span data-ttu-id="1f915-122">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1f915-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f915-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f915-123">See also</span></span>

- [<span data-ttu-id="1f915-124">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f915-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
