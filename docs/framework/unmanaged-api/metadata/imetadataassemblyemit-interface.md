---
title: IMetaDataAssemblyEmit-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a7e4bd68bfd985b8902ae3b2340773ca77eee10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit-Schnittstelle
Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineAssembly-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineAssemblyRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineManifestResource-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[SetAssemblyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|Ändert die angegebene `Assembly`-Metadatenstruktur.|  
|[SetAssemblyRefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|Ändert die angegebene `AssemblyRef`-Metadatenstruktur.|  
|[SetExportedTypeProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|Ändert die angegebene `ExportedType`-Metadatenstruktur.|  
|[SetFileProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|Ändert die angegebene `File`-Metadatenstruktur.|  
|[SetManifestResourceProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|Ändert die angegebene `ManifestResource`-Metadatenstruktur.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
