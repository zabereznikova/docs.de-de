---
title: ISymUnmanagedReader::GetDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 950fb3b9c51ae2c9470b5aadd31c877d7aa6b6f6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615058"
---
# <a name="isymunmanagedreadergetdocument-method"></a>ISymUnmanagedReader::GetDocument-Methode
Sucht ein Dokument. Die Dokument Sprache, der Anbieter und der Typ sind optional.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `url`  
 in Die URL, die das Dokument identifiziert.  
  
 `language`  
 in Die Dokument Sprache. Dieser Parameter ist optional.  
  
 `languageVendor`  
 in Die Identität des Herstellers für die Dokument Sprache. Dieser Parameter ist optional.  
  
 `documentType`  
 in Der Typ des Dokuments. Dieser Parameter ist optional.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
