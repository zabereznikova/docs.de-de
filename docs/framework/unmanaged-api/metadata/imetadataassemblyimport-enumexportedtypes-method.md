---
title: IMetaDataAssemblyImport::EnumExportedTypes-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708893"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes-Methode

Listet die exportierten Typen auf, auf die im Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss ein NULL-Wert sein, wenn die- `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.  
  
 `rExportedTypes`  
 vorgenommen Die Enumeration von `mdExportedType` Metadatentoken.  
  
 `cMax`  
 in Die maximale Anzahl von `mdExportedType` Token, die in das Array eingefügt werden können `rExportedTypes` .  
  
 `pcTokens`  
 vorgenommen Die Anzahl der `mdExportedType` Token, die tatsächlich in platziert wurden `rExportedTypes` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
