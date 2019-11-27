---
title: IMetaDataDispenser-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: b7ce76c22e7188117bddd9e4f328e323f6742685
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436226"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser-Schnittstelle
Stellt Methoden bereit, um einen neuen Metadatenbereich zu erstellen, oder öffnet einen vorhandenen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|Erstellt einen neuen Bereich im Speicher, in dem Sie neue Metadaten erstellen können.|  
|[OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|Öffnet eine vorhandene Datei auf dem Datenträger und ordnet Ihre Metadaten dem Arbeitsspeicher zu.|  
|[OpenScopeOnMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält. Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
