---
title: StrongNameGetBlobFromImage-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 3a84221f94bad76d69f0dc67fe695ada3f3862f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732241"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage-Funktion

Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbBase`  
 in Die Speicheradresse des zugeordneten Assemblymanifests.  
  
 `dwLength`  
 in Die Größe des Bilds in Bytes in `pbBase` .  
  
 `pbBlob`  
 in Ein Puffer, der die binäre Darstellung des Bilds enthalten soll.  
  
 `pcbBlob`  
 [in, out] Die angeforderte maximale Größe von in Bytes `pbBlob` . Bei der Rückgabe die tatsächliche Größe von in Bytes `pbBlob` .  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Wenn die `StrongNameGetBlobFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetBlobFromImage-Methode](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [StrongNameGetBlob-Methode](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
