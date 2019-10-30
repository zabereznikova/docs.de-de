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
ms.openlocfilehash: a8856790b655f071df704879a247169f456ae2f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130873"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize-Funktion
Gibt die Größe der Signatur mit starkem Namen zurück. `StrongNameSignatureSize` wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine verzögert signierte Assembly erstellt wird.  
  
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
 in Die Größe `pbPublicKeyBlob`in Byte.  
  
 `pcbSize`  
 in Die Anzahl der Bytes, die zum Speichern der starken Namens Signatur erforderlich sind.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` nach erfolgreichem Abschluss. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `StrongNameSignatureSize`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureSize-Methode](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
