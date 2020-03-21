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
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177294"
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
 [out] Ein Zeiger auf den neuen Enumerator. Dies muss NULL für den ersten Aufruf dieser Methode sein.  
  
 `rTypeDefs`  
 [in] Das Array, das zum Speichern der TypeDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rTypeDefs`-Arrays.  
  
 `pcTypeDefs`  
 [out] Die Anzahl der in zurückgegebenen `rTypeDefs`TypeDef-Token.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine Token zum Aufzählen vorhanden. In diesem `pcTypeDefs` Fall ist Null.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das TypeDef-Token stellt einen Typ wie eine Klasse oder eine Schnittstelle sowie jeden Typ dar, der über einen Erweiterbarkeitsmechanismus hinzugefügt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
