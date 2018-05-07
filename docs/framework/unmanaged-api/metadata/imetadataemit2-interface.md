---
title: IMetaDataEmit2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 418e5287852b1a8d69d310d2ba71e4f2a3b5d7bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2-Schnittstelle
Erweitert die [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle in erster Linie und die Arbeit mit generischen Typen ermöglicht.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineGenericParam-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Erstellt eine Definition für einen generischen Typparameter, und ruft ein Token an den generischen Typparameter ab.|  
|[DefineMethodSpec-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition.|  
|[GetDeltaSaveSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Ruft einen Wert, der angibt, des Unterschied in der Größe der Daten, die erforderlich sind, um die Änderungen für die aktuelle Sitzung mit bearbeiten und Fortfahren auszudrücken.|  
|[ResetENCLog-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Setzt das Bearbeiten und Fortfahren-Protokoll zurück und startet eine neue Sitzung.|  
|[SaveDelta-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.|  
|[SaveDeltaToMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.|  
|[SaveDeltaToStream-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und Fortfahren im angegebenen Stream.|  
|[SetGenericParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Legt Eigenschaftswerte für die Definition der generischen Parameter durch das angegebene Token verwiesen wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
