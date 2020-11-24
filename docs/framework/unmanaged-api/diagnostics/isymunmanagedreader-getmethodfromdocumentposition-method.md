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
ms.openlocfilehash: 417644e5d0c7af802d5266bd1825efa83c181597
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689601"
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
 vorgenommen Ein Zeiger auf die Adresse eines [ISymUnmanagedMethod-Schnittstellen](isymunmanagedmethod-interface.md) Objekts, das die Methode darstellt, die den Breakpoint enthält.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
