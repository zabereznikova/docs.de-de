---
title: ISymUnmanagedReader::GetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: f0a688aef9fbc6f7bfac85e06cbe7e76704d3230
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720530"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a>ISymUnmanagedReader::GetUserEntryPoint-Methode

Gibt die Methode zurück, die ggf. als Benutzer Einstiegspunkt für das Modul angegeben wurde. Diese Methode kann z. b. die Hauptmethode des Benutzers anstelle der vom Compiler generierten Stub vor der Main-Methode sein.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a>Parameter  

 `pToken`  
 vorgenommen Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
