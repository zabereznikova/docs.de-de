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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c38b7f060c34f7408195484dec2c49305db422fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781322"
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes-Methode
Listet die benutzerdefinierten Attribut-Definition-Token, die den angegebenen Typ oder Member zugeordnet.  
  
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
 [in, out] Ein Zeiger auf die zurückgegebene Enumerator.  
  
 `tk`  
 [in] Ein Token für den Bereich der Enumeration oder 0 (null) für alle benutzerdefinierten Attribute.  
  
 `tkType`  
 [in] Ein Token für den Konstruktor des Typs der Attribute aufgelistet werden sollen, oder `null` für alle Typen.  
  
 `rCustomAttributes`  
 [out] Ein Array von benutzerdefinierten Attribut-Token.  
  
 `cMax`  
 [in] Die maximale Größe des `rCustomAttributes`-Arrays.  
  
 `pcCustomAttributes`  
 [Out, optional] Die tatsächliche Anzahl der token in zurückgegebenen Werte `rCustomAttributes`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es gibt keine benutzerdefinierten Attribute aufgelistet. In diesem Fall `pcCustomAttributes` ist 0 (null).|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
