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
ms.openlocfilehash: 12b97b28383eb7c39f20ee0e88f55d48e60ad956
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494098"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc-Schnittstelle
Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.  
  
> [!NOTE]
> Die- `IMethodMalloc` Schnittstelle ist eine einfache Speicherzuweisung. Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Alloc-Methode](imethodmalloc-alloc-method.md)|Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat. Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
