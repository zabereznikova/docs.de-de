---
title: IMetaDataAssemblyImport-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436309"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport-Schnittstelle
Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseEnum-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Gibt das Handle für den angegebenen Enumerator frei.|  
|[EnumAssemblyRefs-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdAssemblyRef` Token der Assemblys enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumExportedTypes-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdExportedType` Token der com-Typen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumFiles-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdFile` Token der Dateien enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumManifestResources-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdManifestResource` Token der Ressourcen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[FindAssembliesByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen ab.|  
|[FindExportedTypeByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Ruft ein `mdExportedType` Token für den com-Typ mit dem angegebenen Namen ab.|  
|[FindManifestResourceByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ruft ein `mdManifestResource` Token für die Ressource mit dem angegebenen Namen ab.|  
|[GetAssemblyFromScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.|  
|[GetAssemblyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Assembly ab.|  
|[GetAssemblyRefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Ruft die Eigenschafts Einstellungen des angegebenen `mdAssemblyRef` Tokens ab.|  
|[GetExportedTypeProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Ruft die Eigenschafts Einstellungen des angegebenen COM-Typs ab.|  
|[GetFileProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Datei ab.|  
|[GetManifestResourceProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Manifestressource ab.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
