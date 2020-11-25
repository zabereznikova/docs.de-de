---
title: ISymUnmanagedBinder2::GetReaderForFile2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
ms.openlocfilehash: e0fc6cf2a08de4a00cb8b7f98d3922df98f427c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706969"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2-Methode

Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.  
  
 Diese Methode bietet eine ausführlichere Suche nach der Programm Datenbankdatei (PDB) als die [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
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
  
 `pRetVal`  
 vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="remarks"></a>Hinweise  

 Diese Version der-Methode kann nach der PDB-Datei in anderen Bereichen als rechts neben dem-Modul suchen. Die Such Richtlinie kann durch Kombinieren von [corsymsearchpolicyattribute](corsymsearchpolicyattributes-enumeration.md)gesteuert werden. Sucht z. b. `AllowReferencePathAccess | AllowSymbolServerAccess` nach der PDB neben der ausführbaren Datei und auf einem Symbol Server, fragt jedoch nicht die Registrierung ab oder verwendet den Pfad in der ausführbaren Datei. Wenn der- `searchPath` Parameter bereitgestellt wird, werden diese Verzeichnisse immer durchsucht.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedBinder2-Schnittstelle](isymunmanagedbinder2-interface.md)
- [GetReaderForFile-Methode](isymunmanagedbinder-getreaderforfile-method.md)
