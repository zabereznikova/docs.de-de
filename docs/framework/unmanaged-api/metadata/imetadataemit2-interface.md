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
ms.openlocfilehash: 87b5b60d75d5d28e100ec75192d0cacf51765927
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200193"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2-Schnittstelle
Erweitert die [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle, in erster Linie um die Möglichkeit bieten, die Arbeit mit generischen Typen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineGenericParam-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Erstellt eine Definition für einen generischen Typparameter, und ruft ein Token an den generischen Typparameter ab.|  
|[DefineMethodSpec-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Erstellt eine generische Instanz einer Methode und ruft ein Token an der Definition ab.|  
|[GetDeltaSaveSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Ruft einen Wert, der angibt, des Unterschied in der Größe der Daten, die erforderlich sind, um die Änderungen für die aktuelle Sitzung mit bearbeiten und Fortfahren auszudrücken.|  
|[ResetENCLog-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Setzt das Bearbeiten und Fortfahren-Protokoll, und startet eine neue Sitzung.|  
|[SaveDelta-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.|  
|[SaveDeltaToMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.|  
|[SaveDeltaToStream-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in den angegebenen Stream.|  
|[SetGenericParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Legt Eigenschaftswerte für die generischen Parameter-Definition, die auf die verwiesen wird durch das angegebene Token fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
