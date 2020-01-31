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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860968"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc-Schnittstelle
Stellt eine Methode zum Zuordnen von Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) bereit.  
  
> [!NOTE]
> Die `IMethodMalloc`-Schnittstelle ist eine einfache Speicherzuweisung. Dadurch können Sie Arbeitsspeicher zuweisen, aber nicht freigeben.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Alloc-Methode](imethodmalloc-alloc-method.md)|Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Zuweisung ist Modul spezifisch und stellt sicher, dass der Funktions Rumpf einen positiven Offset von der Basis des Moduls hat. Der Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein. Daher sollte die Zuweisung verwendet werden, um Speicher nur für einen Funktions Rumpf zuzuweisen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
