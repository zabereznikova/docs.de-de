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
ms.openlocfilehash: 2bdfe65dbf923ec61d91a259b5257d892fef53da
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007337"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser-Schnittstelle
Stellt Methoden bereit, um einen neuen Metadatenbereich zu erstellen, oder öffnet einen vorhandenen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineScope-Methode](imetadatadispenser-definescope-method.md)|Erstellt einen neuen Bereich im Speicher, in dem Sie neue Metadaten erstellen können.|  
|[OpenScope-Methode](imetadatadispenser-openscope-method.md)|Öffnet eine vorhandene Datei auf dem Datenträger und ordnet Ihre Metadaten dem Arbeitsspeicher zu.|  
|[OpenScopeOnMemory-Methode](imetadatadispenser-openscopeonmemory-method.md)|Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält. Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [Metadatenschnittstellen](metadata-interfaces.md)
