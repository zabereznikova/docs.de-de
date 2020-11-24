---
title: ISymUnmanagedWriter2::DefineLocalVariable2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: cdbb09d25f51e479a8a8ddfc23348305ba7c0a71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683419"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="41fff-102">ISymUnmanagedWriter2::DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="41fff-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>

<span data-ttu-id="41fff-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="41fff-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="41fff-104">Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt.</span><span class="sxs-lookup"><span data-stu-id="41fff-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="41fff-105">In diesem Fall dürfen sich die Werte des `startOffset` -Parameters und des- `endOffset` Parameters jedoch nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="41fff-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fff-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41fff-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41fff-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="41fff-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="41fff-108">in Der Name der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="41fff-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="41fff-109">in Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="41fff-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="41fff-110">in Das Metadatentoken der Signatur.</span><span class="sxs-lookup"><span data-stu-id="41fff-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="41fff-111">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="41fff-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="41fff-112">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="41fff-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="41fff-113">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="41fff-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="41fff-114">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="41fff-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="41fff-115">in Der Anfangs Offset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="41fff-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="41fff-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="41fff-116">This parameter is optional.</span></span> <span data-ttu-id="41fff-117">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="41fff-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="41fff-118">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="41fff-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="41fff-119">in Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="41fff-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="41fff-120">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="41fff-120">This parameter is optional.</span></span> <span data-ttu-id="41fff-121">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="41fff-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="41fff-122">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="41fff-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41fff-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41fff-123">Return Value</span></span>  

 <span data-ttu-id="41fff-124">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="41fff-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fff-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41fff-125">Requirements</span></span>  

 <span data-ttu-id="41fff-126">**Header:** Corsym. idl</span><span class="sxs-lookup"><span data-stu-id="41fff-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fff-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41fff-127">See also</span></span>

- [<span data-ttu-id="41fff-128">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41fff-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="41fff-129">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="41fff-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
