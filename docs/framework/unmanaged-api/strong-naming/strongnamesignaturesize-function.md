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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798958"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize-Funktion
Gibt die Größe der Signatur mit starkem Namen zurück. `StrongNameSignatureSize`wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine verzögert signierte Assembly erstellt wird.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) -Methode.  
  
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
 in Eine Struktur vom Typ [PublicKeyBlob](publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.  
  
 `cbPublicKeyBlob`  
 in Die Größe von `pbPublicKeyBlob`in Bytes.  
  
 `pcbSize`  
 in Die Anzahl der Bytes, die zum Speichern der starken Namens Signatur erforderlich sind.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`nach erfolgreichem Abschluss: `false`andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `StrongNameSignatureSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureSize-Methode](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
