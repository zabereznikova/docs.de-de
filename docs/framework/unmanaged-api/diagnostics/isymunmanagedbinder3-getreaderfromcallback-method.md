---
title: ISymUnmanagedBinder3::GetReaderFromCallback-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449312"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback-Methode
Ermöglicht es dem Benutzer, über einen Rückruf entweder eine `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` zu implementieren oder bereitzustellen, um die debugverzeichnisinformationen aus dem Arbeitsspeicher abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `importer`  
 in Ein Zeiger auf die Schnittstelle für den Metadatenimport.  
  
 `fileName`  
 in Ein Zeiger auf den Dateinamen.  
  
 `searchPath`  
 in Ein Zeiger auf den Suchpfad.  
  
 `searchPolicy`  
 in Ein Wert der [corsymsearchpolicyattribute](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) -Enumeration, der die Richtlinie angibt, die bei einer Suche nach einem Symbol Leser verwendet werden soll.  
  
 `callback`  
 in Ein Zeiger auf die Rückruffunktion.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedBinder3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
