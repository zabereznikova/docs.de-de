---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 5afd48b36355835647ab8d06691f2bd2058b00cb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426737"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode
Gibt die Methode zurück, die den Breakpoint an der angegebenen Position in einem Dokument enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `document`  
 in Das angegebene Dokument.  
  
 `line`  
 in Die Zeile des angegebenen Dokuments.  
  
 `column`  
 in Die Spalte des angegebenen Dokuments.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf die Adresse eines [ISymUnmanagedMethod-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Objekts, das die Methode darstellt, die den Breakpoint enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
