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
ms.openlocfilehash: 7a2a5080872f49a84e36c53ac337d91738c15e45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501338"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter-Schnittstelle
Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo-Methode](imetadataconverter-getmetadatafromtypeinfo-method.md)|Ruft einen Zeiger auf eine [IMetaDataImport](imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, auf die von der angegebenen-Instanz verwiesen wird `ITypeInfo` .|  
|[GetMetaDataFromTypeLib-Methode](imetadataconverter-getmetadatafromtypelib-method.md)|Ruft einen Zeiger auf eine- `IMetaDataImport` Instanz ab, die die Metadatensignatur für die Typbibliothek darstellt, die von der angegebenen-Instanz dargestellt wird `ITypeLib` .|  
|[GetTypeLibFromMetaData-Methode](imetadataconverter-gettypelibfrommetadata-method.md)|Ruft einen Zeiger auf eine- `ITypeLib` Instanz ab, die die Typbibliothek darstellt, die über die angegebenen Module und Bibliotheksnamen verfügt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
