---
title: GetPublicKeyToken-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
ms.openlocfilehash: e41be6407076a2609a83a5be3b0c42d28914ec38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720341"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken-Methode

Ruft das Token des öffentlichen Schlüssels für eine angegebene keyfile oder einen Schlüssel Container ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `pszKeyFile`  
 Der Dateiname des Schlüssels.  
  
 `pszKeyContainer`  
 Der Name des Schlüssel Containers.  
  
 `pvPublicKeyToken`  
 Adresse, an der das Schlüssel Token gespeichert werden soll.  
  
 `pcbPublicKeyToken`  
 Gibt die Größe (in Bytes) des Puffers an, der durch angegeben wird `pvPublicKeyToken` . Enthält bei der Rückgabe die tatsächliche Anzahl der verwendeten Bytes.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [ALink-API](index.md)
