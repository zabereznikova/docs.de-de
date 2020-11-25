---
title: StrongNameGetBlob-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 8f5cb89294004dfb1f020627ceb1edb58735f72c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732280"
---
# <a name="strongnamegetblob-function"></a>StrongNameGetBlob-Funktion

Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszFilePath`  
 in Ein gültiger Pfad zur ausführbaren Datei, die geladen werden soll.  
  
 `pbBlob`  
 in Der Puffer, in den die ausführbare Datei geladen werden soll.  
  
 `pcbBlob`  
 [in, out] Die angeforderte maximale Größe von in Bytes `pbBlob` . Bei der Rückgabe die tatsächliche Größe von in Bytes `pbBlob` .  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Wenn die `StrongNameGetBlob` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetBlob-Methode](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [StrongNameGetBlobFromImage-Methode](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
