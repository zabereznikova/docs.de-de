---
title: ISymUnmanagedVariable::GetAddressField1-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: 253fd17178c03bc0c4d8ea031888a404ad56f876
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615279"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a>ISymUnmanagedVariable::GetAddressField1-Methode
Ruft das erste Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der das erste Adressfeld empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedVariable-Schnittstelle](isymunmanagedvariable-interface.md)
- [GetAddressField2-Methode](isymunmanagedvariable-getaddressfield2-method.md)
- [GetAddressField3-Methode](isymunmanagedvariable-getaddressfield3-method.md)
- [GetAddressKind-Methode](isymunmanagedvariable-getaddresskind-method.md)
