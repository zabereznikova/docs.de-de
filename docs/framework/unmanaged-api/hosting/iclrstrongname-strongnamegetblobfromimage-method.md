---
title: ICLRStrongName::StrongNameGetBlobFromImage-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: 82e18db2f5b911f0e7895959119edd7d2c722f3b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763129"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>ICLRStrongName::StrongNameGetBlobFromImage-Methode
Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
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
 `S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetBlob-Methode](iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
