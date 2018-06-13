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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 532f69afd949971fbb4f56a8fdbcc6eab159446f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427706"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>ISymUnmanagedWriter::DefineDocument-Methode
Definiert ein Quelldokument. GUIDs werden für bekannte Sprachen, Hersteller und Dokumenttypen bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a>Parameter  
 `url`  
 [in] Ein Zeiger auf eine `WCHAR` , definiert den uniform Resource Locator (URL), die das Dokument kennzeichnet.  
  
 `language`  
 [in] Ein Zeiger auf eine GUID, die die Dokumentsprache definiert.  
  
 `languageVendor`  
 [in] Ein Zeiger auf eine GUID, die die Identität des Herstellers für die Dokumentsprache definiert.  
  
 `documentType`  
 [in] Ein Zeiger auf eine GUID, die den Typ des Dokuments definiert.  
  
 `pRetVal`  
 [out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
