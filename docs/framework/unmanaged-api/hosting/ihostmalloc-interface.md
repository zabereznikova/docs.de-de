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
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804600"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, differenzierte Zuordnungen aus dem Heap über den Host anzufordern.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Alloc-Methode](ihostmalloc-alloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist.|  
|[DebugAlloc-Methode](ihostmalloc-debugalloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.|  
|[Free-Methode](ihostmalloc-free-method.md)|Gibt Arbeitsspeicher frei, der mithilfe der-Methode zugeordnet wurde `Alloc` .|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft einen Schnittstellen Zeiger auf eine-Instanz ab, `IHostMalloc` indem die [IHostMemoryManager:: createmzuzugsmethode](ihostmemorymanager-createmalloc-method.md) aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
