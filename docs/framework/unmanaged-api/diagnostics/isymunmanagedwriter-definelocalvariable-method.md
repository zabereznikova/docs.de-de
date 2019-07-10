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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9466df3f6413f86eb8558f0037b96c254b2a2e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777340"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="1b7f7-102">ISymUnmanagedWriter::DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="1b7f7-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="1b7f7-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="1b7f7-104">Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="1b7f7-105">In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7f7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b7f7-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1b7f7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b7f7-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1b7f7-108">[in] Ein Zeiger auf eine `WCHAR` , die Namen den lokalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="1b7f7-109">[in] Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="1b7f7-110">[in] Ein `ULONG32` , die Größe in Bytes angibt, der die `signature` Puffer.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="1b7f7-111">[in] Die Signatur der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="1b7f7-112">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="1b7f7-113">[in] Die erste Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="1b7f7-114">[in] Die zweite Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="1b7f7-115">[in] Die dritte Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="1b7f7-116">[in] Der Anfangsoffset der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="1b7f7-117">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-117">This parameter is optional.</span></span> <span data-ttu-id="1b7f7-118">Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="1b7f7-119">Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="1b7f7-120">[in] Der Endoffset der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="1b7f7-121">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-121">This parameter is optional.</span></span> <span data-ttu-id="1b7f7-122">Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="1b7f7-123">Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b7f7-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b7f7-124">Return Value</span></span>  
 <span data-ttu-id="1b7f7-125">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7f7-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b7f7-126">Requirements</span></span>  
 <span data-ttu-id="1b7f7-127">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1b7f7-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7f7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b7f7-128">See also</span></span>

- [<span data-ttu-id="1b7f7-129">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b7f7-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="1b7f7-130">DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="1b7f7-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="1b7f7-131">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="1b7f7-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
