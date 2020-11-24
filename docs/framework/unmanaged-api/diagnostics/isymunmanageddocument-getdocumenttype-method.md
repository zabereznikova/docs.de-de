---
title: ISymUnmanagedDocument::GetDocumentType-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: d30ee9318d76aaf3ad2cde789ae292aed54f457e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689679"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a>ISymUnmanagedDocument::GetDocumentType-Methode

Ruft den Dokumenttyp dieses Dokuments ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `pRetVal`  
 vorgenommen Ein Zeiger auf eine Variable, die den Dokumenttyp empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)
