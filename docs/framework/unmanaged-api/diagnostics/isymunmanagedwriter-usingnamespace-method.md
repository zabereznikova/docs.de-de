---
title: ISymUnmanagedWriter::UsingNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
ms.openlocfilehash: 6404252f2c1eb14f0cd723451beb82b4c65960fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683484"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a>ISymUnmanagedWriter::UsingNamespace-Methode

Gibt an, dass der angegebene voll qualifizierte Namespace Name innerhalb des derzeit geöffneten lexikalischen Gültigkeits Bereichs verwendet wird. Der-Namespace wird innerhalb aller Bereiche verwendet, die vom derzeit geöffneten Bereich erben. Wenn Sie den aktuellen Bereich schließen, wird auch die Verwendung des-Namespaces beendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a>Parameter  

 `fullName`  
 in Ein Zeiger auf den voll qualifizierten Namen des Namespace.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
