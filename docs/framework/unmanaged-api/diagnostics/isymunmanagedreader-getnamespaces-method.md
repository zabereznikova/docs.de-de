---
title: ISymUnmanagedReader::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5227de340bec85620f8c8d45538ad9a9d7f688fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630956"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a>ISymUnmanagedReader::GetNamespaces-Methode
Ruft die Namespaces, die auf diesem Symbolspeicher mit globalem Gültigkeitsbereich definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cNameSpaces`  
 [in] Die Größe des Namespacearrays.  
  
 `pcNameSpaces`  
 [out] Ein Zeiger auf eine Variable, die die Länge der Liste der Namespaces empfängt.  
  
 `namespaces`  
 [out] Ein Zeiger auf eine Variable, die der Liste der Namespaces empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
