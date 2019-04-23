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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136499"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls-Methode
Listet alle Schnittstellen implementiert, mit dem angegebenen `TypeDef`. 
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `td`  
 [in] Das Token der TypeDef, die schnittstellenimplementierungen darstellen, deren MethodDef-Token sind, aufgelistet werden sollen.  
  
 `rImpls`  
 [out] Das Array zum Speichern der MethodDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rImpls`-Arrays.  
  
 `pcImpls`  
 [out] Die tatsächliche Anzahl der in zurückgegebenen Token `rImpls`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine MethodDef-Token aufgelistet werden. In diesem Fall `pcImpls` auf 0 (null) festgelegt ist.|  

## <a name="remarks"></a>Hinweise

Die Enumeration gibt eine Auflistung von `mdInterfaceImpl` -Token für jede Schnittstelle implementiert, mit dem angegebenen `TypeDef`. Interface-Token in der Reihenfolge, die die Schnittstellen angegeben wurden. zurückgegeben werden (über `DefineTypeDef` oder `SetTypeDefProps`). Eigenschaften des zurückgegebenen `mdInterfaceImpl` Token können abgefragt werden, mithilfe von [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
