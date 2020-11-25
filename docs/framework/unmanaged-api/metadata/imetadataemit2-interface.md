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
ms.openlocfilehash: b8ad159dace734c343297b256092162f17ab829b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726482"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2-Schnittstelle

Erweitert die [IMetaDataEmit](imetadataemit-interface.md) -Schnittstelle hauptsächlich, um die Möglichkeit zu bieten, mit generischen Typen zu arbeiten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineGenericParam-Methode](imetadataemit2-definegenericparam-method.md)|Erstellt eine Definition für einen generischen Typparameter und ruft ein Token für diesen generischen Typparameter ab.|  
|[DefineMethodSpec-Methode](imetadataemit2-definemethodspec-method.md)|Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition ab.|  
|[GetDeltaSaveSize-Methode](imetadataemit2-getdeltasavesize-method.md)|Ruft einen Wert ab, der den Unterschied in der Größe der Daten angibt, die zum Ausdrücken der Änderungen für die aktuelle Edit-and-Continue-Sitzung erforderlich sind.|  
|[ResetENCLog-Methode](imetadataemit2-resetenclog-method.md)|Setzt das Edit-and-Continue-Protokoll zurück und startet eine neue Sitzung.|  
|[SaveDelta-Methode](imetadataemit2-savedelta-method.md)|Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in der angegebenen Datei.|  
|[SaveDeltaToMemory-Methode](imetadataemit2-savedeltatomemory-method.md)|Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in den Arbeitsspeicher.|  
|[SaveDeltaToStream-Methode](imetadataemit2-savedeltatostream-method.md)|Speichert Änderungen aus der aktuellen Edit-and-Continue-Sitzung in den angegebenen Stream.|  
|[SetGenericParamProps-Methode](imetadataemit2-setgenericparamprops-method.md)|Legt Eigenschaftswerte für die generische Parameterdefinition fest, auf die durch das angegebene Token verwiesen wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
