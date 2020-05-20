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
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614694"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="66142-102">ISymUnmanagedWriter2::DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="66142-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="66142-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="66142-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="66142-104">Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt.</span><span class="sxs-lookup"><span data-stu-id="66142-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="66142-105">In diesem Fall dürfen sich die Werte des `startOffset` -Parameters und des- `endOffset` Parameters jedoch nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="66142-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66142-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="66142-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="66142-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="66142-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="66142-108">in Der Name der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="66142-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="66142-109">in Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="66142-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="66142-110">in Das Metadatentoken der Signatur.</span><span class="sxs-lookup"><span data-stu-id="66142-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="66142-111">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="66142-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="66142-112">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="66142-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="66142-113">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="66142-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="66142-114">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="66142-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="66142-115">in Der Anfangs Offset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="66142-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="66142-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="66142-116">This parameter is optional.</span></span> <span data-ttu-id="66142-117">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="66142-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="66142-118">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="66142-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="66142-119">in Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="66142-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="66142-120">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="66142-120">This parameter is optional.</span></span> <span data-ttu-id="66142-121">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="66142-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="66142-122">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="66142-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66142-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66142-123">Return Value</span></span>  
 <span data-ttu-id="66142-124">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="66142-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66142-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66142-125">Requirements</span></span>  
 <span data-ttu-id="66142-126">**Header:** Corsym. idl</span><span class="sxs-lookup"><span data-stu-id="66142-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66142-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66142-127">See also</span></span>

- [<span data-ttu-id="66142-128">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66142-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="66142-129">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="66142-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
