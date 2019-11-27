---
title: IMethodMalloc-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447552"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc-Schnittstelle
Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.  
  
> [!NOTE]
> Die `IMethodMalloc`-Schnittstelle ist eine einfache Speicherzuweisung. Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alloc-Methode](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat. Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
