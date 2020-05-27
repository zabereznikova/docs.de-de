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
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009014"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport-Schnittstelle
Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CloseEnum-Methode](imetadataassemblyimport-closeenum-method.md)|Gibt das Handle für den angegebenen Enumerator frei.|  
|[EnumAssemblyRefs-Methode](imetadataassemblyimport-enumassemblyrefs-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die Token der Assemblys enthält, `mdAssemblyRef` auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumExportedTypes-Methode](imetadataassemblyimport-enumexportedtypes-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdExportedType` Token der com-Typen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumFiles-Methode](imetadataassemblyimport-enumfiles-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdFile` Token der Dateien enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumManifestResources-Methode](imetadataassemblyimport-enummanifestresources-method.md)|Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdManifestResource` Token der Ressourcen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[FindAssembliesByName-Methode](imetadataassemblyimport-findassembliesbyname-method.md)|Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen ab.|  
|[FindExportedTypeByName-Methode](imetadataassemblyimport-findexportedtypebyname-method.md)|Ruft ein `mdExportedType` Token für den com-Typ mit dem angegebenen Namen ab.|  
|[FindManifestResourceByName-Methode](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ruft ein `mdManifestResource` Token für die Ressource mit dem angegebenen Namen ab.|  
|[GetAssemblyFromScope-Methode](imetadataassemblyimport-getassemblyfromscope-method.md)|Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.|  
|[GetAssemblyProps-Methode](imetadataassemblyimport-getassemblyprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Assembly ab.|  
|[GetAssemblyRefProps-Methode](imetadataassemblyimport-getassemblyrefprops-method.md)|Ruft die Eigenschafts Einstellungen des angegebenen Tokens ab `mdAssemblyRef` .|  
|[GetExportedTypeProps-Methode](imetadataassemblyimport-getexportedtypeprops-method.md)|Ruft die Eigenschafts Einstellungen des angegebenen COM-Typs ab.|  
|[GetFileProps-Methode](imetadataassemblyimport-getfileprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Datei ab.|  
|[GetManifestResourceProps-Methode](imetadataassemblyimport-getmanifestresourceprops-method.md)|Ruft die Eigenschafts Einstellungen der angegebenen Manifestressource ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
