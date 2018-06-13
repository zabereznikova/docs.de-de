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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455116"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc-Schnittstelle
Bietet eine Methode zum Belegen von Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf.  
  
> [!NOTE]
>  Die `IMethodMalloc` Schnittstelle ist eine einfache Speicherbelegungsfunktion. Sie können Arbeitsspeicher belegt werden, jedoch nicht, um ihn freizugeben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alloc-Methode](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Versucht, eine bestimmte Arbeitsspeichermenge für einen neuen Text des MSIL-Funktion zugeordnet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Zuweisung Modul spezifisch ist, und stellt sicher, dass der Hauptteil der Funktion mit einem positiven Offset von der Basisklasse des Moduls werden. Arbeitsspeicher oberhalb der Basis eines Moduls kann wertvoll sein, damit die Zuweisung zum Reservieren von Speicher nur für einen Funktionsrumpf verwendet werden soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
