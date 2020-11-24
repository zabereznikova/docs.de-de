---
title: ISymUnmanagedWriter2::DefineConstant2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: d45ab56f081bf0a8802b17e338f7b404809f0f16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683471"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a>ISymUnmanagedWriter2::DefineConstant2-Methode

Definiert einen Namen für einen konstanten Wert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a>Parameter  

 `name`  
 in Der Konstantenname.  
  
 `value`  
 in Der Wert der Konstanten.  
  
 `sigToken`  
 in Das Metadatentoken der Konstanten.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter2-Schnittstelle](isymunmanagedwriter2-interface.md)
- [DefineConstant-Methode](isymunmanagedwriter-defineconstant-method.md)
