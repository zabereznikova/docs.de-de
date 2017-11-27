---
title: IMethodMalloc::Alloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae0fa84c08cb8e366db36b6727a3058f24789801
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMethodMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
