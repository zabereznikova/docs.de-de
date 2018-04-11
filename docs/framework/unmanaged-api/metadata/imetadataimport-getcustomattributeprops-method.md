---
title: IMetaDataImport::GetCustomAttributeProps-Methode
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
caps.latest.revision: 14
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1e6ef9443b99b3e6b36154558ce226d421dbc0a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>IMetaDataImport::GetCustomAttributeProps-Methode
Ruft den Wert des benutzerdefinierten Attributs mit dem angegebenen Metadatentoken ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cv`  
 [in] Ein Metadatentoken, das das benutzerdefinierte Attribut darstellt, das abgerufen werden soll.  
  
 `ptkObj`  
 [out, optional] Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut ändert. Dieser Wert kann jeder Typ von Metadatentoken außer `mdCustomAttribute` sein.  
  
 `ptkType`  
 [out, optional] Ein `mdMethodDef`- oder ein `mdMemberRef`-Metadatentoken, das den <xref:System.Type> des zurückgegebenen benutzerdefinierten Attributs darstellt.  
  
 `ppBlob`  
 [out, optional] Ein Zeiger auf ein Datenarray, das der Wert des benutzerdefinierten Attributs ist.  
  
 `pcbSize`  
 [out, optional] Die Größe der in *`ppBlob` zurückgegebenen Daten in Bytes .  
  
## <a name="remarks"></a>Hinweise  
 Ein benutzerdefiniertes Attribut wird als ein Datenarray gespeichert. Dies ist das Format, das vom Metadatenmodul erwartet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
