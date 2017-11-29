---
title: ISymUnmanagedWriter::DefineGlobalVariable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineGlobalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7540dfcefbe7a331a26220a07b2e206c1302ddc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="45eeb-102">ISymUnmanagedWriter::DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="45eeb-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="45eeb-103">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="45eeb-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45eeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45eeb-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45eeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45eeb-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="45eeb-106">[in] Ein Zeiger auf eine `WCHAR` , der Name den globalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="45eeb-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="45eeb-107">[in] Die Attribute der globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="45eeb-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="45eeb-108">[in] Ein `ULONG32` gibt, die die Größe in Zeichen, d. h., der die `signature` Puffer.</span><span class="sxs-lookup"><span data-stu-id="45eeb-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="45eeb-109">[in] Die Signatur der globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="45eeb-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="45eeb-110">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="45eeb-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="45eeb-111">[in] Die erste Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="45eeb-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="45eeb-112">[in] Die zweite Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="45eeb-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="45eeb-113">[in] Die dritte Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="45eeb-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45eeb-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45eeb-114">Return Value</span></span>  
 <span data-ttu-id="45eeb-115">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="45eeb-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45eeb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45eeb-116">Requirements</span></span>  
 <span data-ttu-id="45eeb-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="45eeb-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45eeb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45eeb-118">See Also</span></span>  
 [<span data-ttu-id="45eeb-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45eeb-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="45eeb-120">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="45eeb-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="45eeb-121">DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="45eeb-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
