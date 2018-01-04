---
title: ISymUnmanagedConstant::GetValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetValue
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 15ae3e9f2e680c7e85d3b8daa0d6010773797258
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetvalue-method"></a>ISymUnmanagedConstant::GetValue-Methode
Ruft den Wert der Konstanten ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pValue`  
 [out] Ein Zeiger auf eine Variable, die den Wert empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedConstant-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [GetName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [GetSignature-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
