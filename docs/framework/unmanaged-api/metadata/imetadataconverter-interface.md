---
title: IMetaDataConverter-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc1f813cac237642fdaab653cd47552ab7472ab0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732925"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter-Schnittstelle
Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|Ruft einen Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Signatur der Metadaten für die Typbibliothek, auf die verwiesen wird durch das angegebene darstellt `ITypeInfo` Instanz.|  
|[GetMetaDataFromTypeLib-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|Ruft einen Zeiger auf ein `IMetaDataImport` Instanz, die die Signatur der Metadaten für die Typbibliothek, dargestellt durch das angegebene darstellt `ITypeLib` Instanz.|  
|[GetTypeLibFromMetaData-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|Ruft einen Zeiger auf ein `ITypeLib` -Instanz, die die Typbibliothek darstellt, die die angegebenen Namen der Module und -Bibliothek.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
