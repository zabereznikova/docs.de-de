---
title: IAssemblyCacheItem-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719943"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem-Schnittstelle

Stellt eine einzelne Assembly im globalen Assemblycache dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AbortItem-Methode](iassemblycacheitem-abortitem-method.md)|Ermöglicht es der Assembly im globalen Assemblycache, Cleanupvorgänge auszuführen, bevor Sie freigegeben wird.|  
|[Commit-Methode](iassemblycacheitem-commit-method.md)|Führt einen Commit für den zwischengespeicherten Assemblyverweis zum|  
|[CreateStream-Methode](iassemblycacheitem-createstream-method.md)|Erstellt einen Stream mit dem angegebenen Namen und Format.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
- [IAssemblyCache-Schnittstelle](iassemblycache-interface.md)
