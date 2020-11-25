---
title: ISymUnmanagedVariable::GetStartOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733307"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a>ISymUnmanagedVariable::GetStartOffset-Methode

Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab. Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Start Offset in die für den Bereich definierten Offsets.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der den Start Offset empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedVariable-Schnittstelle](isymunmanagedvariable-interface.md)
- [GetEndOffset-Methode](isymunmanagedvariable-getendoffset-method.md)
