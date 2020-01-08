---
title: IMetaDataImport::EnumInterfaceImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338066"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls-Methode
Listet alle Schnittstellen auf, die durch die angegebene `TypeDef`implementiert werden. 
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `td`  
 in Das Token der typedef, dessen MethodDef-Token, die Schnittstellen Implementierungen darstellen, aufgelistet werden sollen.  
  
 `rImpls`  
 vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.  
  
 `cMax`  
 in Die maximale Länge des `rImpls` Arrays.  
  
 `pcImpls`  
 vorgenommen Die tatsächliche Anzahl von Token, die in `rImpls`zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine MethodDef-Token zum Auflisten vorhanden. In diesem Fall wird `pcImpls` auf 0 (null) festgelegt.|  

## <a name="remarks"></a>Hinweise

Die-Enumeration gibt eine Auflistung von `mdInterfaceImpl`-Token für jede Schnittstelle zurück, die vom angegebenen `TypeDef`implementiert wird. Schnittstellen Token werden in der Reihenfolge zurückgegeben, in der die Schnittstellen angegeben wurden (über `DefineTypeDef` oder `SetTypeDefProps`). Eigenschaften der zurückgegebenen `mdInterfaceImpl` Token können mithilfe von " [getinterfakeimplproperties](imetadataimport-getinterfaceimplprops-method.md)" abgefragt werden.
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
