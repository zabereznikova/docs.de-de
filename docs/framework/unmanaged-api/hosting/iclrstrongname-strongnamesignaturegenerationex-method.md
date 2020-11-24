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
ms.openlocfilehash: 78cc043953e6288df136b43590831569d112afef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674514"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>ICLRStrongName::StrongNameSignatureGenerationEx-Methode

Generiert gemäß den angegebenen Flags eine Signatur mit starkem Namen für die angegebene Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
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
 in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.  
  
 `wszKeyContainer`  
 in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.  
  
 Wenn `pbKeyBlob` NULL ist, `wszKeyContainer` muss einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben. In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.  
  
 Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.  
  
 `pbKeyBlob`  
 in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel. Dieses Paar weist das Format auf, das von der Win32-Funktion erstellt wird `CryptExportKey` . Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von angegebene Schlüssel Container `wszKeyContainer` das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 in Die Größe von in Bytes `pbKeyBlob` .  
  
 `ppbSignatureBlob`  
 vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch angegebenen Datei `wszFilePath` .  
  
 Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll. Der Aufrufer muss diesen Bereich mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.  
  
 `pcbSignatureBlob`  
 vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.  
  
 `dwFlags`  
 in Einer oder mehrere der folgenden Werte:  
  
- `SN_SIGN_ALL_FILES` (0x00000001)-berechnen Sie alle Hashes für verknüpfte Module neu.  
  
- `SN_TEST_SIGN` (0x00000002): Test-Signieren der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Hinweise  

 Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.  
  
 Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber kein öffentlicher Schlüssel enthalten ist (sowohl `pbKeyBlob` als auch `wszFilePath` sind null), werden Hashwerte für verknüpfte Module neu berechnet, die Assembly wird jedoch nicht neu signiert.  
  
 Wenn `SN_TEST_SIGN` angegeben wird, wird der Common Language Runtime-Header nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureGeneration-Methode](iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
