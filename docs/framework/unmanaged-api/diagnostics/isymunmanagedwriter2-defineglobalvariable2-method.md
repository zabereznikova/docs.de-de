---
title: ISymUnmanagedWriter2::DefineGlobalVariable2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineGlobalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d1214a7bc8cb2826e31c310c88bce8158aefd4f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="ed3f6-102">ISymUnmanagedWriter2::DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3f6-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="ed3f6-103">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed3f6-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed3f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed3f6-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ed3f6-106">[in] Der Name der globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ed3f6-107">[in] Die Attribute der globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="ed3f6-108">[in] Das Metadatentoken der Signatur.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ed3f6-109">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ed3f6-110">[in] Die erste Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ed3f6-111">[in] Die zweite Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ed3f6-112">[in] Die dritte Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed3f6-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ed3f6-113">Return Value</span></span>  
 <span data-ttu-id="ed3f6-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ed3f6-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3f6-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed3f6-115">Requirements</span></span>  
 <span data-ttu-id="ed3f6-116">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="ed3f6-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3f6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed3f6-117">See Also</span></span>  
 [<span data-ttu-id="ed3f6-118">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3f6-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="ed3f6-119">DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3f6-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
