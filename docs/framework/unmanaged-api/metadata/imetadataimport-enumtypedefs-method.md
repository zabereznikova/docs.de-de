---
title: IMetaDataImport::EnumTypeDefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720411"
---
# <a name="imetadataimportenumtypedefs-method"></a>IMetaDataImport::EnumTypeDefs-Methode

Zählt TypeDef-Token auf, die alle Typen innerhalb des aktuellen Bereichs darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 vorgenommen Ein Zeiger auf den neuen Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `rTypeDefs`  
 in Das Array, das zum Speichern der TypeDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rTypeDefs`-Arrays.  
  
 `pcTypeDefs`  
 vorgenommen Die Anzahl der in zurückgegebenen TypeDef-Token `rTypeDefs` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTypeDefs` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  

 Das TypeDef-Token stellt einen Typ dar, z. b. eine Klasse oder eine Schnittstelle, sowie alle Typen, die über einen Erweiterbarkeits Mechanismus hinzugefügt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
