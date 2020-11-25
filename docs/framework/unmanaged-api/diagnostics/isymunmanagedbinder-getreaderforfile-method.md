---
title: ISymUnmanagedBinder::GetReaderForFile-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
ms.openlocfilehash: ac895032e70cf31532ab4c73409d6d750eae65df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706995"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a>ISymUnmanagedBinder::GetReaderForFile-Methode

Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.  
  
 Diese Methode öffnet die Programm Datenbankdatei (PDB-Datei) nur dann, wenn Sie sich neben der ausführbaren Datei befindet. Diese Änderung wurde aus Sicherheitsgründen vorgenommen. Wenn Sie eine umfassendere Suche nach der PDB-Datei benötigen, verwenden Sie die [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `importer`  
 in Ein Zeiger auf die Schnittstelle für den Metadatenimport.  
  
 `fileName`  
 in Ein Zeiger auf den Dateinamen.  
  
 `searchPath`  
 in Ein Zeiger auf den Suchpfad.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedBinder-Schnittstelle](isymunmanagedbinder-interface.md)
- [GetReaderForFile2-Methode](isymunmanagedbinder2-getreaderforfile2-method.md)
