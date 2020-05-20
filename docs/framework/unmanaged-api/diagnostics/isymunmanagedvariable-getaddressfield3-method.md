---
title: ISymUnmanagedVariable::GetAddressField3-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: ff888d3e2b86efeea3f4e3d33528f731d85886bf
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615266"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a>ISymUnmanagedVariable::GetAddressField3-Methode
Ruft das dritte Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der das dritte Adressfeld empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedVariable-Schnittstelle](isymunmanagedvariable-interface.md)
- [GetAddressField1-Methode](isymunmanagedvariable-getaddressfield1-method.md)
- [GetAddressField2-Methode](isymunmanagedvariable-getaddressfield2-method.md)
- [GetAddressKind-Methode](isymunmanagedvariable-getaddresskind-method.md)
