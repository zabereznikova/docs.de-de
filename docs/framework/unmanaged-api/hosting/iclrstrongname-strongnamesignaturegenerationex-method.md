---
title: ICLRStrongName::StrongNameSignatureGenerationEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5d2539bc732cdc41c7514fd5d81c449ed8f17a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992887"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>ICLRStrongName::StrongNameSignatureGenerationEx-Methode
Generiert eine Signatur mit starkem Namen für die angegebene Assembly gemäß den angegebenen Flags.  
  
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
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben. In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.  
  
 Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar. Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion. Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, des `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.  
  
 Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück. Der Aufrufer muss diesen Speicherplatz mit Freigeben der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbSignatureBlob`  
 [out] Die Größe in Bytes der zurückgegebenen Signatur.  
  
 `dwFlags`  
 [in] Eine oder mehrere der folgenden Werte:  
  
- `SN_SIGN_ALL_FILES` (0 x 00000001) – alle Hashes für verknüpfte Module neu.  
  
- `SN_TEST_SIGN` (0 x 00000002) - Test Signierung der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.  
  
 Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist. (beide `pbKeyBlob` und `wszFilePath` null sind), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.  
  
 Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureGeneration-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
