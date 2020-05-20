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
ms.openlocfilehash: 4a23e9aa259f430c0d0579657952fc6aba4c307c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441655"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback-Methode
Ermöglicht dem Benutzer das implementieren oder Bereitstellen von per Callback entweder `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` , um die debugverzeichnisinformationen aus dem Arbeitsspeicher abzurufen.  
  
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
 in Ein Wert der [corsymsearchpolicyattribute](corsymsearchpolicyattributes-enumeration.md) -Enumeration, der die Richtlinie angibt, die bei einer Suche nach einem Symbol Leser verwendet werden soll.  
  
 `callback`  
 in Ein Zeiger auf die Rückruffunktion.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedBinder3-Schnittstelle](isymunmanagedbinder3-interface.md)
