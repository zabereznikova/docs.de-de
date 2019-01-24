---
title: IMetaDataImport::GetCustomAttributeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68cac76a83164e24c0810c9d19fa845c8580b1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637236"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName-Methode
Ruft das benutzerdefinierte Attribut, mit dem angegebenen Namen und Besitzer ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tkObj`  
 [in] Ein Metadatentoken, das das Objekt, das Besitzer des benutzerdefinierten Attributs darstellt.  
  
 `szName`  
 [in] Der Name des benutzerdefinierten Attributs.  
  
 `ppData`  
 [out] Ein Zeiger auf ein Array von Daten, die den Wert des benutzerdefinierten Attributs.  
  
 `pcbData`  
 [out] Die Größe in Bytes der Daten im zurückgegebenen *`ppData`.  
  
## <a name="remarks"></a>Hinweise  
 Es ist zulässig, mehrere benutzerdefinierte Attribute für den gleichen Besitzer zu definieren; Sie können auch den gleichen Namen haben. Allerdings `GetCustomAttributeByName` gibt nur eine Instanz zurück. (`GetCustomAttributeByName` gibt die erste Instanz, die es auftritt.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, rufen die [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
