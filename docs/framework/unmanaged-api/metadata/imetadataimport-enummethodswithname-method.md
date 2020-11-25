---
title: IMetaDataImport::EnumMethodsWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720931"
---
# <a name="imetadataimportenummethodswithname-method"></a>IMetaDataImport::EnumMethodsWithName-Methode

Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `cl`  
 in Ein TypeDef-Token, das den Typ darstellt, dessen Methoden aufgelistet werden sollen.  
  
 `szName`  
 in Der Name, der den Bereich der-Enumeration einschränkt.  
  
 `rMethods`  
 vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMethods`-Arrays.  
  
 `pcTokens`  
 vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rMethods` .  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse. Im Gegensatz zu [IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md) `EnumMethodsWithName` verwirft alle Methoden Token, die nicht über den angegebenen Namen verfügen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodsWithName` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token zum Auflisten vorhanden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
