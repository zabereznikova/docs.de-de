---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1571e43d6a89af453d6289ccb646c7222f0a5ad6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742688"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration-Methode
Generiert eine Signatur mit starkem Namen für die angegebene Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben. In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.  
  
 Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Es werden keine anderen Arten von Schlüsseln zu diesem Zeitpunkt unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar. Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion. Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, des `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.  
  
 Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück. Der Aufrufer muss diesen Speicherplatz freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbSignatureBlob`  
 [out] Die Größe in Bytes der zurückgegebenen Signatur.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureGenerationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
