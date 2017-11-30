---
title: ISymUnmanagedVariable::GetEndOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7a2dac8425cd852c6c17ee1674710f6798d3b1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a>ISymUnmanagedVariable::GetEndOffset-Methode
Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab. Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Endoffset innerhalb der Offsets für den Bereich definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [GetStartOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
