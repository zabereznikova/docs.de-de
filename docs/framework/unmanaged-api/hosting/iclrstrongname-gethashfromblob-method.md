---
title: ICLRStrongName::GetHashFromBlob-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714808"
---
# <a name="iclrstrongnamegethashfromblob-method"></a>ICLRStrongName::GetHashFromBlob-Methode

Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbBlob`  
 in Ein Zeiger auf die Adresse des Speicherblocks, für den der Hashwert verwendet werden soll.  
  
 `cchBlob`  
 in Die Länge des Speicherblocks in Bytes.  
  
 `piHashAlg`  
 [in, out] Eine-Konstante, die den Hash Algorithmus angibt. Verwenden Sie 0 (null) für den Standard Algorithmus.  
  
 `pbHash`  
 vorgenommen Der zurückgegebene Hash Puffer.  
  
 `cchHash`  
 in Die angeforderte maximale Größe von `pbHash` .  
  
 `pchHash`  
 vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
