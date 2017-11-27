---
title: ISymUnmanagedVariable::GetAddressField3-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1dfeb3f02b0c767dfc200a625fa4c617692dc11f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="f7db2-102">ISymUnmanagedVariable::GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="f7db2-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="f7db2-103">Ruft das Feld für die dritte Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="f7db2-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="f7db2-104">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="f7db2-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7db2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7db2-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7db2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7db2-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f7db2-107">[out] Ein Zeiger auf eine `ULONG32` , die Feld für die dritte Adresse empfängt.</span><span class="sxs-lookup"><span data-stu-id="f7db2-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7db2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7db2-108">Return Value</span></span>  
 <span data-ttu-id="f7db2-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f7db2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7db2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7db2-110">Requirements</span></span>  
 <span data-ttu-id="f7db2-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7db2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7db2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7db2-112">See Also</span></span>  
 [<span data-ttu-id="f7db2-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7db2-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="f7db2-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="f7db2-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="f7db2-115">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="f7db2-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="f7db2-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="f7db2-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
