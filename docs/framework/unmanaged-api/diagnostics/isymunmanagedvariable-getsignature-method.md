---
title: ISymUnmanagedVariable::GetSignature-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f28d6ec882afb21c3c204e141b1b6d883793004
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499055"
---
# <a name="isymunmanagedvariablegetsignature-method"></a>ISymUnmanagedVariable::GetSignature-Methode
Ruft die Signatur dieser Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cSig`  
 [in] Die Länge des Puffers verweist die `sig` Parameter.  
  
 `pcSig`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Signatur enthalten, die erforderlichen Puffers in Zeichen.  
  
 `sig`  
 [out] Der Puffer, in dem die Signatur gespeichert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
