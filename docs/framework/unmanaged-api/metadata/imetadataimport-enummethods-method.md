---
title: IMetaDataImport::EnumMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 00726b7e74bdedc658886cccbc4329eaf3ae76d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696803"
---
# <a name="imetadataimportenummethods-method"></a>IMetaDataImport::EnumMethods-Methode

Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `cl`  
 in Ein TypeDef-Token, das den Typ mit den aufzuzählenden Methoden darstellt.  
  
 `rMethods`  
 vorgenommen Das Array zum Speichern der MethodDef-Token.  
  
 `cMax`  
 in Die maximale Größe des MethodDef- `rMethods` Arrays.  
  
 `pcTokens`  
 vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rMethods` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumMethods` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine MethodDef-Token zum Auflisten vorhanden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
