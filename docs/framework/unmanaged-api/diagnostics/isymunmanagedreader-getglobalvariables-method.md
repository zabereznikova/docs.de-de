---
title: ISymUnmanagedReader::GetGlobalVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: b6cf7293f1d65db1f60301f49ce655c74df3daca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448316"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a>ISymUnmanagedReader::GetGlobalVariables-Methode
Gibt alle globalen Variablen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cVars`  
 in Die Länge des Puffers, auf den `pcVars`zeigt.  
  
 `pcVars`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der Variablen erforderlich ist.  
  
 `pVars`  
 vorgenommen Ein Puffer, der die Variablen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
