---
title: ISymUnmanagedWriter::RemapToken-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683556"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>ISymUnmanagedWriter::RemapToken-Methode

Benachrichtigt den Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, während die Metadaten ausgegeben wurden. Wenn der Symbolwriter das alte Token im Symbol Speicher gespeichert hat, muss entweder das gespeicherte Token mit dem neuen Wert aktualisiert werden, oder es muss die Zuordnung gespeichert werden, damit der entsprechende Symbol Reader während der Lese Phase neu zugeordnet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Parameter  

 `oldToken`  
 in Das Metadatentoken, das neu zugeordnet wurde.  
  
 `newToken`  
 in Das neue Metadatentoken, dem neu zugeordnet `oldToken` wurde.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
