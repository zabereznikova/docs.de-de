---
title: ICLRStrongName::StrongNameSignatureGenerationEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 247bcfa3c9f7a02dea331ff14948a00812fb06e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>ICLRStrongName::StrongNameSignatureGenerationEx-Methode
Generiert eine starke Namenssignatur für die angegebene Assembly gemäß den angegebenen Flags.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur des starken Namens generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` ist null, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben. In diesem Fall wird das Schlüsselpaar in dem Container gespeichert verwendet, um die Datei zu signieren.  
  
 Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar. Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion. Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, der `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` ist null, die Common Language Runtime speichert-Signatur in der Datei gemäß `wszFilePath`.  
  
 Wenn `ppbSignatureBlob` ist ungleich null, die common Language Runtime reserviert Speicherplatz in dem die Signatur zurückgegeben. Der Aufrufer muss diesen Speicherplatz mit Freigeben der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbSignatureBlob`  
 [out] Die Größe in Bytes, der zurückgegebenen Signatur.  
  
 `dwFlags`  
 [in] Eine oder mehrere der folgenden Werte:  
  
-   `SN_SIGN_ALL_FILES`(0 x 00000001) – alle Hashes für verknüpfte Module neu.  
  
-   `SN_TEST_SIGN`(0 x 00000002) - Test Signierung der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie null für `wszFilePath` auf die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.  
  
 Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist (beide `pbKeyBlob` und `wszFilePath` sind null), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.  
  
 Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureGeneration-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
