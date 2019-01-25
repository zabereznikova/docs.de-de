---
title: ISymUnmanagedNamespace::GetVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a5eb01a3e354b4360bea59af1e63ffeb0576aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730112"
---
# <a name="isymunmanagednamespacegetvariables-method"></a>ISymUnmanagedNamespace::GetVariables-Methode
Gibt alle Variablen, die im globalen Gültigkeitsbereich innerhalb dieses Namespace definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cVars`  
 [in] Ein `ULONG32` , der angibt, dass der Größe des der `pVars` Array.  
  
 `pcVars`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Namespaces enthalten.  
  
 `pVars`  
 [out] Ein Zeiger auf einen Puffer, der die Namespaces enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedNamespace-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
