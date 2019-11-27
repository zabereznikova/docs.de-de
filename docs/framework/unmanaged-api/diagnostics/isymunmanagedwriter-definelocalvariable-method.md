---
title: ISymUnmanagedWriter::DefineLocalVariable-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: f6a741df3ea57b5e9b4fa8bc5d304bfedd1d6c15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428011"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="9aa9c-102">ISymUnmanagedWriter::DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="9aa9c-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="9aa9c-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="9aa9c-104">Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="9aa9c-105">In diesem Fall dürfen sich die Werte der Parameter "`startOffset`" und "`endOffset`" jedoch nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa9c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9aa9c-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aa9c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9aa9c-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9aa9c-108">in Ein Zeiger auf einen `WCHAR`, der den Namen der lokalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="9aa9c-109">in Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="9aa9c-110">in Ein-`ULONG32`, der die Größe des `signature` Puffers in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="9aa9c-111">in Die Signatur der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="9aa9c-112">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="9aa9c-113">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="9aa9c-114">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="9aa9c-115">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="9aa9c-116">in Der Anfangs Offset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="9aa9c-117">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-117">This parameter is optional.</span></span> <span data-ttu-id="9aa9c-118">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="9aa9c-119">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="9aa9c-120">in Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="9aa9c-121">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-121">This parameter is optional.</span></span> <span data-ttu-id="9aa9c-122">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="9aa9c-123">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aa9c-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9aa9c-124">Return Value</span></span>  
 <span data-ttu-id="9aa9c-125">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9aa9c-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aa9c-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9aa9c-126">Requirements</span></span>  
 <span data-ttu-id="9aa9c-127">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="9aa9c-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa9c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aa9c-128">See also</span></span>

- [<span data-ttu-id="9aa9c-129">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9aa9c-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="9aa9c-130">DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="9aa9c-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="9aa9c-131">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="9aa9c-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
