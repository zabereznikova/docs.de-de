---
title: ISymUnmanagedScope::GetStartOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b81ac93c67d59c294f22eb825527fa9982d9124
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721096"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a>ISymUnmanagedScope::GetStartOffset-Methode
Ruft den Anfangsoffset für diesen Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Ein Zeiger auf eine `ULONG32` , die das Anfangsoffset enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [GetEndOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
