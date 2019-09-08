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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796704"
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
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
- [IAssemblyCache-Schnittstelle](iassemblycache-interface.md)
