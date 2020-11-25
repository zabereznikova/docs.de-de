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
ms.openlocfilehash: 89556cf0e1ef65c35278a526e10fc791063ea2c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708347"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey-Funktion

Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt. Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) -Methode.  
  
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
 in Eine Struktur vom Typ [PublicKeyBlob](publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.  
  
 `cbPublicKeyBlob`  
 in Die Größe von in Bytes `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 vorgenommen Das Token für den starken Namen, das dem übergebenen Schlüssel entspricht `pbPublicKeyBlob` . Der Common Language Runtime ordnet den Speicher zu, in den das Token zurückgegeben werden soll. Der Aufrufer muss diesen Arbeitsspeicher mithilfe der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.  
  
 `pcbStrongNameToken`  
 vorgenommen Die Größe (in Bytes) des zurückgegebenen Token für den starken Namen.  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, mit dem Speicherplatz beim Speichern von Schlüsselinformationen in Metadaten eingespart wird. Insbesondere werden starke namens Token in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.  
  
 Wenn die `StrongNameTokenFromPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameTokenFromPublicKey-Methode](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey-Methode](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob-Struktur](publickeyblob-structure.md)
