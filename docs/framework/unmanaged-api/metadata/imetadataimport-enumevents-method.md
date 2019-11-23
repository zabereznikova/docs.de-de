---
title: IMetaDataImport::EnumEvents-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440009"
---
# <a name="imetadataimportenumevents-method"></a>IMetaDataImport::EnumEvents-Methode
Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] A pointer to the enumerator.  
  
 `td`  
 [in] The TypeDef token whose event definitions are to be enumerated.  
  
 `rEvents`  
 [out] The array of returned events.  
  
 `cMax`  
 [in] Die maximale Größe des `rEvents`-Arrays.  
  
 `pcEvents`  
 [out] The actual number of events returned in `rEvents`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumEvents` returned successfully.|  
|`S_FALSE`|There are no events to enumerate. In that case, `pcEvents` is zero.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Included as a resource in MsCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
