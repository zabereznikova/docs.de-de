---
title: ISymUnmanagedWriter2::DefineLocalVariable2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineLocalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 595cc3d8c503a5a6b2cbcb6665f7ff8aff5044d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="19302-102">ISymUnmanagedWriter2::DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="19302-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="19302-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="19302-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="19302-104">Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich aufweist.</span><span class="sxs-lookup"><span data-stu-id="19302-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="19302-105">In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="19302-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19302-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="19302-106">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="19302-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="19302-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="19302-108">[in] Der Name der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="19302-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="19302-109">[in] Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="19302-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="19302-110">[in] Das Metadatentoken der Signatur.</span><span class="sxs-lookup"><span data-stu-id="19302-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="19302-111">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="19302-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="19302-112">[in] Die erste Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="19302-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="19302-113">[in] Die zweite Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="19302-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="19302-114">[in] Die dritte Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="19302-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="19302-115">[in] Der Anfangsoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="19302-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="19302-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="19302-116">This parameter is optional.</span></span> <span data-ttu-id="19302-117">Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="19302-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="19302-118">Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="19302-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="19302-119">[in] Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="19302-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="19302-120">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="19302-120">This parameter is optional.</span></span> <span data-ttu-id="19302-121">Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="19302-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="19302-122">Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="19302-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19302-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19302-123">Return Value</span></span>  
 <span data-ttu-id="19302-124">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="19302-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19302-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19302-125">Requirements</span></span>  
 <span data-ttu-id="19302-126">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="19302-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19302-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19302-127">See Also</span></span>  
 [<span data-ttu-id="19302-128">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19302-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="19302-129">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="19302-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
