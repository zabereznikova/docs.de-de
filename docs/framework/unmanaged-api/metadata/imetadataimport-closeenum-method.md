---
title: IMetaDataImport::CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 724660cd5703ee9b893493df5d583d97b5bdfb3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720521"
---
# <a name="imetadataimportcloseenum-method"></a>IMetaDataImport::CloseEnum-Methode
Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hEnum`  
 [in] Das Handle für den Enumerator zu schließen.  
  
## <a name="remarks"></a>Hinweise  
 Das Handle, das vom angegebenen `hEnum` abgerufen wird, von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
