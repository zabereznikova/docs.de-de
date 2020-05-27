---
title: IMetaDataDispenserEx-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008052"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx-Schnittstelle
Erweitert die Schnittstelle der [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md) und bietet die Möglichkeit, zu steuern, wie die Metadaten-APIs mit dem aktuellen Metadatenbereich arbeiten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[FindAssembly-Methode](imetadatadispenserex-findassembly-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[FindAssemblyModule-Methode](imetadatadispenserex-findassemblymodule-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[GetCORSystemDirectory-Methode](imetadatadispenserex-getcorsystemdirectory-method.md)|Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält. Diese Methode wird nur für die Verwendung durch out-of-Process-debuggger unterstützt. Wenn Sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[GetOption-Methode](imetadatadispenserex-getoption-method.md)|Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.|  
|[OpenScopeOnITypeInfo-Methode](imetadatadispenserex-openscopeonitypeinfo-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[SetOption-Methode](imetadatadispenserex-setoption-method.md)|Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
