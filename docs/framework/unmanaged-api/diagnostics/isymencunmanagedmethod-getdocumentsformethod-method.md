---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176629"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a>ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode
Ruft die Dokumente ab, in denen diese Methode Zeilen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cDocs`  
 [in] Die Länge des Puffers, auf den von `pcDocs`verwiesen wird.  
  
 `pcDocs`  
 [out] Ein Zeiger auf `ULONG32` eine, der die Größe des Puffers in Zeichen empfängt, der erforderlich ist, um die Dokumente zu enthalten.  
  
 `documents`  
 [in] Der Puffer, der die Dokumente enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, ob die Methode erfolgreich ist. andernfalls ein Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Kopfzeile:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
