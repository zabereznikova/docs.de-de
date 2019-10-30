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
ms.openlocfilehash: 5ed0075da1429c70900750f3f28e8ce36a41fb28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134538"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache-Schnittstelle
Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateAssemblyCacheItem-Methode](iassemblycache-createassemblycacheitem-method.md)|Ruft einen Verweis auf ein neues [IAssemblyCacheItem](iassemblycacheitem-interface.md)-Element ab.|  
|[CreateAssemblyScavenger-Methode](iassemblycache-createassemblyscavenger-method.md)|Reserviert für die interne Verwendung durch die Fusion-Technologie.|  
|[InstallAssembly-Methode](iassemblycache-installassembly-method.md)|Installiert die angegebene Assembly im globalen Assemblycache.|  
|[QueryAssemblyInfo-Methode](iassemblycache-queryassemblyinfo-method.md)|Ruft die angeforderten Daten zur angegebenen Assembly ab.|  
|[UninstallAssembly-Methode](iassemblycache-uninstallassembly-method.md)|Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
