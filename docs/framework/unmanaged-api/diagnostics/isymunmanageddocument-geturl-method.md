---
title: ISymUnmanagedDocument::GetURL-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a447de2bb01e7bbf838ef5443e3ae7951bf8226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431366"
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL-Methode
Gibt die URL (uniform Resource Locator) für dieses Dokument zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchUrl`  
 [in] Die Größe des `szURL`-Puffers in Zeichen.  
  
 `pcchUrl`  
 [out] Ein Zeiger auf eine Variable, die Größe der URL, einschließlich der null-Terminierung empfängt.  
  
 `szUrl`  
 [out] Der Puffer, der die URL.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
