---
title: IMetaDataDispenserEx-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx
helpviewer_keywords: IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cf062029647d4834118a459db378c8535182daf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx-Schnittstelle
Erweitert die [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) Schnittstelle bieten die Möglichkeit zum Steuern, wie die Metadaten-APIs im aktuellen Metadatenbereich ausgeführt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FindAssembly-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[FindAssemblyModule-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[GetCORSystemDirectory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Ruft das Verzeichnis, das die aktuelle common Language Runtime (CLR) enthält. Diese Methode ist nur für die Verwendung von Out-of-Process-Debugger unterstützt. Wenn aus einer anderen Komponente aufgerufen wird, gibt es E_NOTIMPL zurück.|  
|[GetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.|  
|[OpenScopeOnITypeInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.|  
|[SetOption-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
