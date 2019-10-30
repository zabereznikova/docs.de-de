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
ms.openlocfilehash: 9ab6fcb64e4654302e411d4dcc587df2e0bf1dc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125190"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration-Funktion
Generiert eine Signatur mit starkem Namen für die angegebene Assembly.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) -Methode.  
  
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
 in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.  
  
 `wszKeyContainer`  
 in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.  
  
 Wenn `pbKeyBlob` NULL ist, muss `wszKeyContainer` einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben. In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.  
  
 Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein. Zurzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel. Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird. Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `wszKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 in Die Größe `pbKeyBlob`in Byte.  
  
 `ppbSignatureBlob`  
 vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch `wszFilePath`angegebenen Datei.  
  
 Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll. Der Aufrufer muss diesen Bereich mit der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.  
  
 `pcbSignatureBlob`  
 vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` nach erfolgreichem Abschluss. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.  
  
 Wenn die `StrongNameSignatureGeneration`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureGeneration-Methode](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [StrongNameSignatureGenerationEx-Methode](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
