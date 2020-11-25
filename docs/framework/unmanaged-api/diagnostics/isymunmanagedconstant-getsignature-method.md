---
title: ISymUnmanagedConstant::GetSignature-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 4436e4528c1dc486eb5c443c5a9467ac69a26c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706930"
---
# <a name="isymunmanagedconstantgetsignature-method"></a>ISymUnmanagedConstant::GetSignature-Methode

Ruft die Signatur der Konstante ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cSig`  
 in Die Länge des Puffers, auf den der- `pcSig` Parameter verweist.  
  
 `pcSig`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Signatur enthalten muss, in Zeichen empfängt.  
  
 `sig`  
 vorgenommen Der Puffer, in dem die Signatur gespeichert wird.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedConstant-Schnittstelle](isymunmanagedconstant-interface.md)
- [GetName-Methode](isymunmanagedconstant-getname-method.md)
- [GetValue-Methode](isymunmanagedconstant-getvalue-method.md)
