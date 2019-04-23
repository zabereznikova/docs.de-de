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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96475086b1244ae75ed692dd10cb693af0be9af7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186952"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx-Schnittstelle
Erweitert die [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) Schnittstelle bieten die Möglichkeit, die steuern, wie die Metadaten-APIs im aktuellen Metadatenbereich ausgeführt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FindAssembly-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Diese Methode ist nicht implementiert. Wird aufgerufen, gibt E_NOTIMPL zurück.|  
|[FindAssemblyModule-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Diese Methode ist nicht implementiert. Wird aufgerufen, gibt E_NOTIMPL zurück.|  
|[GetCORSystemDirectory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Ruft das Verzeichnis, das die aktuelle common Language Runtime (CLR enthält) ab. Diese Methode wird nur für die Verwendung von Out-of-Process-Debugger unterstützt. Wenn aus einer anderen Komponente aufgerufen wird, wird er E_NOTIMPL zurückgeben.|  
|[GetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.|  
|[OpenScopeOnITypeInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Diese Methode ist nicht implementiert. Wird aufgerufen, gibt E_NOTIMPL zurück.|  
|[SetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
