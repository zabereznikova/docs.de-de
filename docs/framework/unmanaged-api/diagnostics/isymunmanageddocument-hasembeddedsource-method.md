---
title: ISymUnmanagedDocument::HasEmbeddedSource-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688197"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a>ISymUnmanagedDocument::HasEmbeddedSource-Methode

Gibt zurück, `true` Wenn das Dokument in die Debugsymbole eingebettet ist; andernfalls wird zurückgegeben `false` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `pRetVal`  
 vorgenommen Ein Zeiger auf eine Variable, die angibt, ob das Dokument in die Debugsymbole eingebettet ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)
