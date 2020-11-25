---
title: ISymUnmanagedVariable::GetEndOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: cf4179f839b62409d5b2185f3e11e8e732c29187
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721867"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a>ISymUnmanagedVariable::GetEndOffset-Methode

Ruft den Endoffset dieser Variablen in ihrem übergeordneten Element ab. Wenn es sich um eine lokale Variable innerhalb eines Bereichs handelt, fällt der Endoffset in die für den Bereich definierten Offsets.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der den Endoffset empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedVariable-Schnittstelle](isymunmanagedvariable-interface.md)
- [GetStartOffset-Methode](isymunmanagedvariable-getstartoffset-method.md)
