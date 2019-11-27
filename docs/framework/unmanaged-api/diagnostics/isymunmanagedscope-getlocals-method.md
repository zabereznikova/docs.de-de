---
title: ISymUnmanagedScope::GetLocals-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: bf932b63973f93c56883f099ddaadd9d1519f337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446330"
---
# <a name="isymunmanagedscopegetlocals-method"></a>ISymUnmanagedScope::GetLocals-Methode
Ruft die in diesem Bereich definierten lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cLocals`  
 in Ein-`ULONG32`, der die Größe des `locals` Arrays angibt.  
  
 `pcLocals`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der lokalen Variablen erforderlich ist.  
  
 `locals`  
 vorgenommen Das Array, das die lokalen Variablen empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
