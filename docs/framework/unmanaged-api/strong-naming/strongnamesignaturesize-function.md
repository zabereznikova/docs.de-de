---
title: StrongNameSignatureSize-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176889"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize-Funktion
Gibt die Größe der Signatur mit starkem Namen zurück. `StrongNameSignatureSize`wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine mit Verzögerung signierte Assembly erstellt wird.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::StrongNameSignatureSize-Methode.](../hosting/iclrstrongname-strongnamesignaturesize-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a>Parameter  
 `pbPublicKeyBlob`  
 [in] Eine Struktur vom Typ [PublicKeyBlob,](publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.  
  
 `cbPublicKeyBlob`  
 [in] Die Größe von in `pbPublicKeyBlob`Bytes von .  
  
 `pcbSize`  
 [in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich sind.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `StrongNameSignatureSize` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureSize-Methode](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
