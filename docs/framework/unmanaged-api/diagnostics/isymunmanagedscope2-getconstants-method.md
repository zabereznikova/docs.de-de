---
title: ISymUnmanagedScope2::GetConstants-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: f7cd45a90a750c357706f720453ff23697875b58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446240"
---
# <a name="isymunmanagedscope2getconstants-method"></a>ISymUnmanagedScope2::GetConstants-Methode
Ruft die in diesem Bereich definierten lokalen Konstanten ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cConstants`  
 in Die Länge des Puffers, auf den der `pcConstants`-Parameter verweist.  
  
 `pcConstants`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers, der die Konstanten enthalten muss, in Zeichen empfängt.  
  
 `constants`  
 vorgenommen Der Puffer, in dem die Konstanten gespeichert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedScope2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
