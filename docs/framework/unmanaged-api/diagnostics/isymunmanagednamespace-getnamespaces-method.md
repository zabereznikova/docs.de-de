---
title: ISymUnmanagedNamespace::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: 48c50ac6be6d525676d85578e5a55a27104c180a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615097"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a>ISymUnmanagedNamespace::GetNamespaces-Methode
Ruft die untergeordneten Elemente dieses Namespace ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cNameSpaces`  
 in Ein-Wert `ULONG32` , der die Größe des `namespaces` Arrays angibt.  
  
 `pcNameSpaces`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Namespaces enthalten muss, in Zeichen empfängt.  
  
 `namespaces`  
 vorgenommen Ein Zeiger auf den Puffer, der die Namespaces enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedNamespace-Schnittstelle](isymunmanagednamespace-interface.md)
