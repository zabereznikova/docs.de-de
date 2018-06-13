---
title: IAssemblyCache-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430582"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache-Schnittstelle
Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateAssemblyCacheItem-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).|  
|[CreateAssemblyScavenger-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Reserviert für interne Verwendung durch die Fusion-Technologie.|  
|[InstallAssembly-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|Wird die angegebene Assembly im globalen Assemblycache installiert.|  
|[QueryAssemblyInfo-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|Ruft die angeforderten Daten über die angegebene Assembly ab.|  
|[UninstallAssembly-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|Wird die angegebene Assembly aus dem globalen Assemblycache deinstalliert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
