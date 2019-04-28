---
title: ISymUnmanagedVariable::GetAttributes-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7ba794060330de3934f8d4ca6434b09672d12bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797565"
---
# <a name="isymunmanagedvariablegetattributes-method"></a>ISymUnmanagedVariable::GetAttributes-Methode
Ruft die Attributflags für diese Variable ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Attribute. Der zurückgegebene Wert werden die Werte in definierten die [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) Enumeration.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
