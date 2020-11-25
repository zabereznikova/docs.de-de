---
title: IMetaDataImport::CountEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: f2470cd7112adff35ef49c21a155072fcd4008be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727288"
---
# <a name="imetadataimportcountenum-method"></a>IMetaDataImport::CountEnum-Methode

Ruft die Anzahl der Elemente in der-Enumeration ab, die vom angegebenen Enumerator abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `hEnum`  
 in Das Handle für den Enumerator.  
  
 `pulCount`  
 vorgenommen Die Anzahl der aufgezählten Elemente.  
  
## <a name="remarks"></a>Hinweise  

 Das Handle, das von angegeben `hEnum` wird, wird von einem vorherigen `Enum` *namens* -Ruf abgerufen (z. b. [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
