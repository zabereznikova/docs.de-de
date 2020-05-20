---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614954"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode
Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `document`  
 in Das angegebene Dokument.  
  
 `line`  
 in Die Zeile des angegebenen Dokuments.  
  
 `column`  
 in Die Spalte des angegebenen Dokuments.  
  
 `cMethod`  
 [in] Die Größe des `pRetVal`-Arrays.  
  
 `pcMethod`  
 vorgenommen Ein Zeiger auf eine Variable, die die Anzahl der im Array zurückgegebenen Elemente empfängt `pRetVal` .  
  
 `pRetVal`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) -Objekt verweist, das eine Methode darstellt, die den Breakpoint enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
