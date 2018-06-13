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
ms.openlocfilehash: d6f8b896d50bb659897291d7bf85e836482611a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428985"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="25e83-102">ISymUnmanagedWriter::DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="25e83-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="25e83-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="25e83-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="25e83-104">Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich aufweist.</span><span class="sxs-lookup"><span data-stu-id="25e83-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="25e83-105">In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="25e83-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25e83-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="25e83-106">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="25e83-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="25e83-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="25e83-108">[in] Ein Zeiger auf eine `WCHAR` , der Name die lokale Variable definiert.</span><span class="sxs-lookup"><span data-stu-id="25e83-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="25e83-109">[in] Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="25e83-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="25e83-110">[in] Ein `ULONG32` gibt, die die Größe in Bytes, der die `signature` Puffer.</span><span class="sxs-lookup"><span data-stu-id="25e83-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="25e83-111">[in] Die Signatur der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="25e83-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="25e83-112">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="25e83-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="25e83-113">[in] Die erste Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="25e83-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="25e83-114">[in] Die zweite Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="25e83-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="25e83-115">[in] Die dritte Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="25e83-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="25e83-116">[in] Der Anfangsoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="25e83-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="25e83-117">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="25e83-117">This parameter is optional.</span></span> <span data-ttu-id="25e83-118">Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="25e83-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="25e83-119">Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="25e83-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="25e83-120">[in] Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="25e83-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="25e83-121">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="25e83-121">This parameter is optional.</span></span> <span data-ttu-id="25e83-122">Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="25e83-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="25e83-123">Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="25e83-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25e83-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="25e83-124">Return Value</span></span>  
 <span data-ttu-id="25e83-125">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="25e83-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25e83-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25e83-126">Requirements</span></span>  
 <span data-ttu-id="25e83-127">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="25e83-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e83-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25e83-128">See Also</span></span>  
 [<span data-ttu-id="25e83-129">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25e83-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="25e83-130">DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="25e83-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="25e83-131">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="25e83-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
