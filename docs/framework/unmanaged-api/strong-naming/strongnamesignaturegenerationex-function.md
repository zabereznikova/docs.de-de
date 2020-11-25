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
ms.openlocfilehash: 96dae519d73505a30c8593e9883da7338525ea2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708516"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx-Funktion

Generiert gemäß den angegebenen Flags eine Signatur mit starkem Namen für die angegebene Assembly.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
 Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll. Der Aufrufer muss diesen Bereich mit der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.  
  
 `pcbSignatureBlob`  
 vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.  
  
 `dwFlags`  
 in Einer oder mehrere der folgenden Werte:  
  
- `SN_SIGN_ALL_FILES` (0x00000001)-berechnen Sie alle Hashes für verknüpfte Module neu.  
  
- `SN_TEST_SIGN` (0x00000002): Test-Signieren der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.  
  
 Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber kein öffentlicher Schlüssel enthalten ist (sowohl `pbKeyBlob` als auch `wszFilePath` sind null), werden Hashwerte für verknüpfte Module neu berechnet, die Assembly wird jedoch nicht neu signiert.  
  
 Wenn `SN_TEST_SIGN` angegeben wird, wird der Common Language Runtime-Header nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.  
  
 Wenn die `StrongNameSignatureGenerationEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureGenerationEx-Methode](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration-Methode](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
