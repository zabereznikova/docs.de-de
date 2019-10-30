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
ms.openlocfilehash: 2493b5338824e1eab3f82a9023bbcced59a98fc8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134468"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem-Schnittstelle
Stellt eine einzelne Assembly im globalen Assemblycache dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AbortItem-Methode](iassemblycacheitem-abortitem-method.md)|Ermöglicht es der Assembly im globalen Assemblycache, Cleanupvorgänge auszuführen, bevor Sie freigegeben wird.|  
|[Commit-Methode](iassemblycacheitem-commit-method.md)|Führt einen Commit für den zwischengespeicherten Assemblyverweis zum|  
|[CreateStream-Methode](iassemblycacheitem-createstream-method.md)|Erstellt einen Stream mit dem angegebenen Namen und Format.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
- [IAssemblyCache-Schnittstelle](iassemblycache-interface.md)
