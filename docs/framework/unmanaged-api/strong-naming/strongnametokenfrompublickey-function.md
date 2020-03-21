---
title: StrongNameTokenFromPublicKey-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175056"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey-Funktion
Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt. Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::StrongNameTokenFromPublicKey-Methode.](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbPublicKeyBlob`  
 [in] Eine Struktur vom Typ [PublicKeyBlob,](publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.  
  
 `cbPublicKeyBlob`  
 [in] Die Größe von in `pbPublicKeyBlob`Bytes von .  
  
 `ppbStrongNameToken`  
 [out] Das Token mit starkem Namen, das dem in `pbPublicKeyBlob`übergebenen Schlüssel entspricht. Die Common Language Runtime weist den Speicher zu, in dem das Token zurückgegeben werden soll. Der Aufrufer muss diesen Speicher mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freizugeben.  
  
 `pcbStrongNameToken`  
 [out] Die Größe des zurückgegebenen Tokens für starken Namen in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, der zum Speichern von Schlüsselinformationen in Metadaten verwendet wird. Insbesondere werden Token mit starkem Namen in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.  
  
 Wenn `StrongNameTokenFromPublicKey` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameTokenFromPublicKey-Methode](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey-Methode](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob-Struktur](publickeyblob-structure.md)
