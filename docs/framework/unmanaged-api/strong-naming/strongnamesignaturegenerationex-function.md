---
title: StrongNameSignatureGenerationEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60825cb82097e6ec9c202efebe04a50b0f5a3771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508611"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx-Funktion
Generiert eine Signatur mit starkem Namen für die angegebene Assembly gemäß den angegebenen Flags.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
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
  
 Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück. Der Aufrufer muss diesen Speicherplatz mit Freigeben der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.  
  
 `pcbSignatureBlob`  
 [out] Die Größe in Bytes der zurückgegebenen Signatur.  
  
 `dwFlags`  
 [in] Eine oder mehrere der folgenden Werte:  
  
-   `SN_SIGN_ALL_FILES` (0 x 00000001) – alle Hashes für verknüpfte Module neu.  
  
-   `SN_TEST_SIGN` (0 x 00000002) - Test Signierung der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.  
  
 Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist. (beide `pbKeyBlob` und `wszFilePath` null sind), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.  
  
 Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.  
  
 Wenn die `StrongNameSignatureGenerationEx` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [StrongNameSignatureGenerationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
