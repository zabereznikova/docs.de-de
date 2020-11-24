---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690521"
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets-Methode

Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `tk`  
 in Ein Metadatentoken, das den Suchbereich einschränkt, oder NULL, um den größtmöglichen Bereich zu durchsuchen.  
  
 `dwActions`  
 in Flags, die die <xref:System.Security.Permissions.SecurityAction> Werte darstellen, die in eingeschlossen werden sollen `rPermission` , oder NULL, um alle Aktionen zurückzugeben.  
  
 `rPermission`  
 vorgenommen Das Array, das zum Speichern der Berechtigungs Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rPermission`-Arrays.  
  
 `pcTokens`  
 vorgenommen Die Anzahl der in zurückgegebenen Berechtigungs Token `rPermission` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
