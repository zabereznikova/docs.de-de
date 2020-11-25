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
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726937"
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL-Methode

Gibt die URL (Uniform Resource Serverlocatorpunkt) für dieses Dokument zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchUrl`  
 [in] Die Größe des `szURL`-Puffers in Zeichen.  
  
 `pcchUrl`  
 vorgenommen Ein Zeiger auf eine Variable, die die Größe der URL erhält, einschließlich der NULL-Beendigung.  
  
 `szUrl`  
 vorgenommen Der Puffer, der die URL enthält.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)
