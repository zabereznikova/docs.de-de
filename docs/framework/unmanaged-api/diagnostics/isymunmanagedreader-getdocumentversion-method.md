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
ms.openlocfilehash: c2cc541b2a78f16d5ca6b19405794faa825a9d72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615032"
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
