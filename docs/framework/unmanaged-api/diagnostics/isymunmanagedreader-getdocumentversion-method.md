---
title: ISymUnmanagedReader::GetDocumentVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707567"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion-Methode

Ruft die angegebene Version des angegebenen Dokuments ab. Die Dokument Version beginnt bei 1 und wird jedes Mal um 1 erhöht, wenn das Dokument mithilfe der [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) -Methode aktualisiert wird. Wenn der- `pbCurrent` Parameter ist `true` , ist dies die neueste Version des Dokuments.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>Parameter  

 `pDoc`  
 in Das angegebene Dokument.  
  
 `version`  
 vorgenommen Ein Zeiger auf eine Variable, die die Version des angegebenen Dokuments empfängt.  
  
 `pbCurrent`  
 vorgenommen Ein Zeiger auf eine Variable, die empfängt `true` , wenn dies die neueste Version des Dokuments ist, oder, `false` Wenn Sie nicht die neueste Version ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
