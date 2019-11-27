---
title: ISymUnmanagedMethod::GetRanges-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: 1f1bd9c33f24847eae4ff7d26c5b996cd34afb72
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448925"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="020c2-102">ISymUnmanagedMethod::GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="020c2-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="020c2-103">Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="020c2-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="020c2-104">Das Array ist ein Array aus ganzen Zahlen und hat das Format [Start, End, Start, End].</span><span class="sxs-lookup"><span data-stu-id="020c2-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="020c2-105">Die Anzahl der Bereichs Paare ist die Länge des Arrays dividiert durch 2.</span><span class="sxs-lookup"><span data-stu-id="020c2-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="020c2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="020c2-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="020c2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="020c2-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="020c2-108">in Das Dokument, für das der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="020c2-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="020c2-109">in Die Dokument Zeile, die den Bereichen entspricht.</span><span class="sxs-lookup"><span data-stu-id="020c2-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="020c2-110">in Die Dokument Spalte, die den Bereichen entspricht.</span><span class="sxs-lookup"><span data-stu-id="020c2-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="020c2-111">[in] Die Größe des `ranges`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="020c2-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="020c2-112">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der Bereiche erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="020c2-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="020c2-113">vorgenommen Ein Zeiger auf den Puffer, der die Bereiche empfängt.</span><span class="sxs-lookup"><span data-stu-id="020c2-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="020c2-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="020c2-114">Return Value</span></span>  
 <span data-ttu-id="020c2-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="020c2-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="020c2-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="020c2-116">Requirements</span></span>  
 <span data-ttu-id="020c2-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="020c2-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020c2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="020c2-118">See also</span></span>

- [<span data-ttu-id="020c2-119">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="020c2-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
