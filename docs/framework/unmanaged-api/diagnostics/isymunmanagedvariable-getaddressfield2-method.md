---
title: ISymUnmanagedVariable::GetAddressField2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ecde3a59c3a393057f3502c8ae59d789350b913f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="3da10-102">ISymUnmanagedVariable::GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="3da10-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="3da10-103">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="3da10-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="3da10-104">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="3da10-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da10-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3da10-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3da10-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3da10-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3da10-107">[out] Ein Zeiger auf eine `ULONG32` , die Feld für die zweite Adresse empfängt.</span><span class="sxs-lookup"><span data-stu-id="3da10-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da10-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3da10-108">Return Value</span></span>  
 <span data-ttu-id="3da10-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3da10-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da10-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3da10-110">Requirements</span></span>  
 <span data-ttu-id="3da10-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3da10-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da10-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da10-112">See Also</span></span>  
 [<span data-ttu-id="3da10-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da10-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="3da10-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="3da10-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="3da10-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="3da10-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="3da10-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="3da10-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
