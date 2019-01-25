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
ms.openlocfilehash: 32bf25140da66448bda1a8827aa40942d896d53f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734950"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser-Schnittstelle
Stellt Methoden zum Erstellen eines neuen Metadaten-Bereichs, oder öffnen Sie eine vorhandene Ressourcengruppe.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.|  
|[OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|Öffnet eine vorhandene, auf dem Datenträger-Datei, und seine Metadaten in den Arbeitsspeicher zugeordnet.|  
|[OpenScopeOnMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält. Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, die in der die vorhandenen Daten als Metadaten behandelt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
