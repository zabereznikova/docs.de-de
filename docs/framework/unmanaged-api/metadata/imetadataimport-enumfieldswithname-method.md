---
title: IMetaDataImport::EnumFieldsWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177339"
---
# <a name="imetadataimportenumfieldswithname-method"></a>IMetaDataImport::EnumFieldsWithName-Methode
Zählt FieldDef-Token des angegebenen Typs mit dem angegebenen Namen auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `cl`  
 [in] Das Token des Typs, dessen Felder aufgezählt werden sollen.  
  
 `szName`  
 [in] Der Feldname, der den Umfang der Enumeration einschränkt.  
  
 `rFields`  
 [out] Array, das zum Speichern der FieldDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rFields`-Arrays.  
  
 `pcTokens`  
 [out] Die tatsächliche Anzahl der FieldDef-Token, die in `rFields`zurückgegeben werden.  
  
## <a name="remarks"></a>Bemerkungen  
 Im Gegensatz zu [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md) `EnumFieldsWithName` verwirft alle Feldtoken, die nicht den angegebenen Namen haben.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine Felder zum Aufzählen vorhanden. In diesem `pcTokens` Fall ist Null.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
