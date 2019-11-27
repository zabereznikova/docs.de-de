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
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440241"
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
 in Ein Token für den Konstruktor des Typs der Attribute, die aufgelistet werden sollen, oder für alle Typen `null`.  
  
 `rCustomAttributes`  
 vorgenommen Ein Array von benutzerdefinierten Attribut Token.  
  
 `cMax`  
 [in] Die maximale Größe des `rCustomAttributes`-Arrays.  
  
 `pcCustomAttributes`  
 [out, optional] Die tatsächliche Anzahl der Tokenwerte, die in `rCustomAttributes`zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine benutzerdefinierten Attribute zum Auflisten vorhanden. In diesem Fall `pcCustomAttributes` gleich 0 (null) ist.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
