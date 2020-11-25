---
title: ISymUnmanagedConstant::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: fca7b11a83b5a695feae82fe5f25218f87afbce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732891"
---
# <a name="isymunmanagedconstantgetname-method"></a>ISymUnmanagedConstant::GetName-Methode

Ruft den Namen der Konstante ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchName`  
 in Die Länge des Puffers, auf den der- `szName` Parameter verweist.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe (in Zeichen) des Puffers erhält, der den Namen enthalten muss, einschließlich der NULL-Beendigung.  
  
 `szName`  
 vorgenommen Der Puffer, in dem der Name gespeichert wird.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedConstant-Schnittstelle](isymunmanagedconstant-interface.md)
- [GetSignature-Methode](isymunmanagedconstant-getsignature-method.md)
- [GetValue-Methode](isymunmanagedconstant-getvalue-method.md)
