---
title: IMetaDataAssemblyImport::EnumAssemblyRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 18cd9dd14e615a7e76bfff30c9ae584305bd1907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708937"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>IMetaDataAssemblyImport::EnumAssemblyRefs-Methode

Listet die `mdAssemblyRef` im Assemblymanifest definierten-Instanzen auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss ein NULL-Wert sein, wenn die- `EnumAssemblyRefs` Methode zum ersten Mal aufgerufen wird.  
  
 `rAssemblyRefs`  
 vorgenommen Die Enumeration von `mdAssemblyRef` Metadatentoken.  
  
 `cMax`  
 in Die maximale Anzahl von Token, die in das Array eingefügt werden können `rAssemblyRefs` .  
  
 `pcTokens`  
 vorgenommen Die Anzahl der Token, die tatsächlich in platziert wurden `rAssemblyRefs` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
