---
title: ISymUnmanagedBinder::GetReaderFromStream-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 955a2b63c457342d6aa31755ce42e989cc791e5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776853"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a>ISymUnmanagedBinder::GetReaderFromStream-Methode
Gibt bei Angabe einer Metadaten-Schnittstelle und ein Stream, der den Symbolspeicher enthält, die richtige [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `importer`  
 [in] Ein Zeiger auf die Metadatenimport-Schnittstelle.  
  
 `pstream`  
 [in] Ein Zeiger auf den Stream, der den Symbolspeicher enthält.  
  
 `pRetVal`  
 [out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedBinder-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
