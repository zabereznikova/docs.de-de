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
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447455"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls-Methode
Zählt MethodDef-Token auf, die Schnittstellenimplementierungen darstellen.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `td`  
 [in] Das Token der TypeDef, die schnittstellenimplementierungen darstellen, deren MethodDef-Token werden aufgelistet werden sollen.  
  
 `rImpls`  
 [out] Das Array zum Speichern der MethodDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rImpls`-Arrays.  
  
 `pcImpls`  
 [out] Die tatsächliche Anzahl der im zurückgegebenen Token `rImpls`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine MethodDef-Token, aufgelistet werden. In diesem Fall `pcImpls` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
