---
title: ISymUnmanagedWriter::DefineDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 6413935df86b85a959fa4f354c6233d18baf99d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727574"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>ISymUnmanagedWriter::DefineDocument-Methode

Definiert ein Quelldokument. GUIDs werden für bekannte Sprachen, Anbieter und Dokumenttypen bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `url`  
 in Ein Zeiger auf einen `WCHAR` , der die URL (Uniform Resource Serverlocatorpunkt) definiert, die das Dokument identifiziert.  
  
 `language`  
 in Ein Zeiger auf eine GUID, die die Dokument Sprache definiert.  
  
 `languageVendor`  
 in Ein Zeiger auf eine GUID, die die Identität des Herstellers für die Dokument Sprache definiert.  
  
 `documentType`  
 in Ein Zeiger auf eine GUID, die den Typ des Dokuments definiert.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
