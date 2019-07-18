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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efe4d28d207625f00634087b862d76c001518c8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777024"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion-Methode
Ruft die angegebene Version des angegebenen Dokuments ab. Die Version beginnt bei 1 und wird erhöht, jeder Aktualisierung des Dokuments wird mithilfe der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) Methode. Wenn die `pbCurrent` Parameter `true`, dies ist die neueste Version des Dokuments.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDoc`  
 [in] Das angegebene Dokument.  
  
 `version`  
 [out] Ein Zeiger auf eine Variable, die Version des angegebenen Dokuments empfängt.  
  
 `pbCurrent`  
 [out] Ein Zeiger auf eine Variable, empfängt `true` ist dies die neueste Version des Dokuments oder `false` Falls sie nicht, dass die neueste Version ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
