---
title: ISymUnmanagedMethod::GetScopeFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 4eefd019280f501a6ce194e5ce84388e32cc66e1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615136"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a>ISymUnmanagedMethod::GetScopeFromOffset-Methode
Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt. Hiermit können lokale Variablen suchen gestartet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `offset`  
 in Ein-Wert `ULONG` , der den Offset enthält.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](isymunmanagedmethod-interface.md)
