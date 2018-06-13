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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b7c183a6ef61b97920fef5c80b4abad50da25bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444869"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser-Schnittstelle
Stellt Methoden zum Erstellen eines neuen Bereichs für die Metadaten oder ein vorhandenes öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.|  
|[OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|Öffnet eine Datei vorhandene, auf dem Datenträger, und seine Metadaten in den Arbeitsspeicher zugeordnet.|  
|[OpenScopeOnMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält. Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, in denen die vorhandenen Daten als Metadaten behandelt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
