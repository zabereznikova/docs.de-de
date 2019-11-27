---
title: IMetaDataImport::EnumParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: e5fa3647c86d97730e7ad6a2576dd34af75251d6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433955"
---
# <a name="imetadataimportenumparams-method"></a>IMetaDataImport::EnumParams-Methode
Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `mb`  
 in Ein MethodDef-Token, das die Methode mit den aufzuzählenden Parametern darstellt.  
  
 `rParams`  
 vorgenommen Das Array, das zum Speichern der ParamDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rParams`-Arrays.  
  
 `pcTokens`  
 vorgenommen Die Anzahl der in `rParams`zurückgegebenen ParamDef-Token.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumParams` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTokens` gleich 0 (null) ist.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
