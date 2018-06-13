---
title: COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fbc41ca1366b412c37d6af09e90e3f1b042ba21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449984"
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur
Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`numRanges`|Die Anzahl der Blöcke von Argumenten. Dieser Wert ist, also die Anzahl der [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Strukturen in den `ranges` Array.|  
|`totalArgumentSize`|Die Gesamtgröße aller Argumente. Das heißt, ist dieser Wert die Summe der Argumentlängen.|  
|`ranges`|Ein Array von `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede einen Block von Funktionsargumenten darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Funktion möglicherweise viele Argumente. Diese Argumente können nicht zusammenhängend im Arbeitsspeicher gespeichert werden. Sie können einen Speicherblock, der drei Argumente an einem Ort, einen Speicherblock, der zwei Argumente in einer anderen Stelle und eine abschließende Block eines Arguments in einem anderen Ort verfügen. Diese Argumente werden alle für die gleiche Funktion; Sie sind nur an unterschiedlichen Orten gespeichert.  
  
 Die `COR_PRF_FUNCTION_ARGUMENT_INFO` -Struktur stellt alle Argumente einer einzelnen Funktion dar. Ein Array verwendet, um alle Blöcke von Funktionsargumenten zu verweisen. Für eine einzelne Funktion haben Sie daher eine einzelne `COR_PRF_FUNCTION_ARGUMENT_INFO` -Struktur, die mehrere verweist auf `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede auf eine oder mehrere Argumente der Funktion verweist.  
  
 Argumente, die in Registern gespeichert sind, werden in den Arbeitsspeicher zum Erstellen von Strukturen gefüllt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
