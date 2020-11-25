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
ms.openlocfilehash: d48c2bdd55e487038048f432c5586d49f393118c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706943"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedBinder3-Schnittstelle](isymunmanagedbinder3-interface.md)
