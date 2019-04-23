---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89831261c5da156343cb098ace715495ddafccaf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086090"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>ISymUnmanagedReader::GetSymAttribute-Methode
Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab. Im Gegensatz zu benutzerdefinierten Metadatenattributen befinden sich diese benutzerdefinierten Attribute im Symbolspeicher.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `parent`  
 [in] Das Metadatentoken für das Objekt, das für das das Attribut angefordert wird.  
  
 `name`  
 [in] Ein Zeiger auf die Variable, die das abzurufende Attribut angibt.  
  
 `cBuffer`  
 [in] Die Größe des `buffer`-Arrays.  
  
 `pcBuffer`  
 [out] Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.  
  
 `buffer`  
 [out] Ein Zeiger auf die Variable, die Attributdaten empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
