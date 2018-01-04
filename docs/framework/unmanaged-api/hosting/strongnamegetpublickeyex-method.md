---
title: StrongNameGetPublicKeyEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e94498cc8841a95e1918d3f26bd19256793564ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx-Methode
Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar und gibt einen Hashalgorithmus und eines Signaturalgorithmus.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzKeyContainer`  
 [in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält. Wenn `pbKeyBlob` ist null, `szKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben. In diesem Fall die `StrongNameGetPublicKeyEx` Methode extrahiert den öffentlichen Schlüssel aus dem Schlüsselpaar in dem Container gespeichert.  
  
 Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Zu diesem Zeitpunkt werden keine anderen Arten von Schlüsseln unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar. Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion. Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `szKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, der `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 [out] Der zurückgegebene öffentliche Schlüssel BLOB. Die `ppbPublicKeyBlob` Parameter von der common Language Runtime zugeordnet ist und an den Aufrufer zurückgegeben. Der Aufrufer muss den Arbeitsspeicher freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbPublicKeyBlob`  
 [out] Die Größe des BLOB zurückgegebenen öffentlichen Schlüssels.  
  
 `uHashAlgId`  
 [in] Der Hashalgorithmus für die Assembly. Finden Sie im Abschnitt "Hinweise" eine Liste der zulässigen Werte.  
  
 `uReserved`  
 [in] Für die zukünftige Verwendung reserviert. Der Standardwert ist null.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Der öffentliche Schlüssel ist Bestandteil einer [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die Menge der zulässigen Werte für die `uHashAlgId` Parameter.  
  
|name|Wert|  
|----------|-----------|  
|Keiner|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameTokenFromPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
