---
title: IMethodMalloc::Alloc-Methode
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d73fe16720248d541bac64a432bb6f35d6873b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454980"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc-Methode
Versucht, eine bestimmte Arbeitsspeichermenge für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf belegt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cb`  
 [in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.  
  
## <a name="remarks"></a>Hinweise  
 Der belegte Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das diese Zuweisung zugeordnet ist. In anderen Worten, jede Zuweisung wird für ein bestimmtes Modul erstellt und versucht, mit einem positiven Offset von seiner Basisadresse belegt werden. Wenn `Alloc` nicht belegen kann die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls, unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.  
  
 Die `Alloc` -Methode sollte verwendet werden, zusammen mit den [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMethodMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
