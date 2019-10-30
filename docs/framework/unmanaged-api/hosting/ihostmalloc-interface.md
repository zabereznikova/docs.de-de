---
title: IHostMalloc-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136775"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, differenzierte Zuordnungen aus dem Heap über den Host anzufordern.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist.|  
|[DebugAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.|  
|[Free-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Gibt Arbeitsspeicher frei, der mithilfe der `Alloc`-Methode reserviert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft durch Aufrufen der [IHostMemoryManager:: createmzuzugsmethode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) einen Schnittstellen Zeiger auf eine `IHostMalloc` Instanz ab.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
