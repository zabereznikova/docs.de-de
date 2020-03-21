---
title: StrongNameSignatureGeneration-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176902"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration-Funktion
Generiert eine Signatur mit starkem Namen für die angegebene Assembly.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::StrongNameSignatureGeneration-Methode.](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die die Signatur mit starkem Namen generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` null `wszKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden. In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.  
  
 Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Derzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentliche/private Schlüsselpaar. Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde. Wenn `pbKeyBlob` null ist, wird `wszKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe von in `pbKeyBlob`Bytes von .  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an den die Common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` null, speichert die Laufzeit die Signatur `wszFilePath`in der datei, die von angegeben wird.  
  
 Wenn `ppbSignatureBlob` dies nicht null ist, weist die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll. Der Aufrufer muss diesen Speicherplatz mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freizugeben.  
  
 `pcbSignatureBlob`  
 [out] Die Größe der zurückgegebenen Signatur in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Bemerkungen  
 Geben Sie `wszFilePath` NULL an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.  
  
 Wenn `StrongNameSignatureGeneration` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureGeneration-Methode](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [StrongNameSignatureGenerationEx-Methode](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
