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
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431146"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx-Schnittstelle
Erweitert die Schnittstelle der [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) und bietet die Möglichkeit, zu steuern, wie die Metadaten-APIs mit dem aktuellen Metadatenbereich arbeiten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FindAssembly-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[FindAssemblyModule-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[GetCORSystemDirectory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält. Diese Methode wird nur für die Verwendung durch out-of-Process-debuggger unterstützt. Wenn Sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[GetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.|  
|[OpenScopeOnITypeInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[SetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
