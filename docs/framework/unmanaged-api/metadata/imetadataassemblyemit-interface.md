---
title: IMetaDataAssemblyEmit-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728289"
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit-Schnittstelle

Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineAssembly-Methode](imetadataassemblyemit-defineassembly-method.md)|Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineAssemblyRef-Methode](imetadataassemblyemit-defineassemblyref-method.md)|Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineExportedType-Methode](imetadataassemblyemit-defineexportedtype-method.md)|Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineFile-Methode](imetadataassemblyemit-definefile-method.md)|Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.|  
|[DefineManifestResource-Methode](imetadataassemblyemit-definemanifestresource-method.md)|Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.|  
|[SetAssemblyProps-Methode](imetadataassemblyemit-setassemblyprops-method.md)|Ändert die angegebene `Assembly`-Metadatenstruktur.|  
|[SetAssemblyRefProps-Methode](imetadataassemblyemit-setassemblyrefprops-method.md)|Ändert die angegebene `AssemblyRef`-Metadatenstruktur.|  
|[SetExportedTypeProps-Methode](imetadataassemblyemit-setexportedtypeprops-method.md)|Ändert die angegebene `ExportedType`-Metadatenstruktur.|  
|[SetFileProps-Methode](imetadataassemblyemit-setfileprops-method.md)|Ändert die angegebene `File`-Metadatenstruktur.|  
|[SetManifestResourceProps-Methode](imetadataassemblyemit-setmanifestresourceprops-method.md)|Ändert die angegebene `ManifestResource`-Metadatenstruktur.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
