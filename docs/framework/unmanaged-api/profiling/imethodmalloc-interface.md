---
title: IMethodMalloc-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc
helpviewer_keywords: IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
