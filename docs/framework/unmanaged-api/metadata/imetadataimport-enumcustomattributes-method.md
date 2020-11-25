---
title: IMetaDataImport::EnumCustomAttributes-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 3b12200dae23a7b6a2f6e1654e46fdf74dc90968
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700534"
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes-Methode

Listet benutzerdefinierte Attribut Definitions Token auf, die dem angegebenen Typ oder Member zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den zurückgegebenen Enumerator.  
  
 `tk`  
 in Ein Token für den Bereich der-Enumeration oder 0 (null) für alle benutzerdefinierten Attribute.  
  
 `tkType`  
 in Ein Token für den Konstruktor des Typs der Attribute, die aufgelistet werden sollen, oder `null` für alle Typen.  
  
 `rCustomAttributes`  
 vorgenommen Ein Array von benutzerdefinierten Attribut Token.  
  
 `cMax`  
 [in] Die maximale Größe des `rCustomAttributes`-Arrays.  
  
 `pcCustomAttributes`  
 [out, optional] Die tatsächliche Anzahl der Tokenwerte, die in zurückgegeben werden `rCustomAttributes` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine benutzerdefinierten Attribute zum Auflisten vorhanden. In diesem Fall `pcCustomAttributes` ist 0 (null).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
