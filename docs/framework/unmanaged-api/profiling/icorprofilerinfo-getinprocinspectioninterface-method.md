---
title: ICorProfilerInfo::GetInprocInspectionInterface-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9088389df33b079fe2275f5c7e642a055fa8ee51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a>ICorProfilerInfo::GetInprocInspectionInterface-Methode
Ruft ein Objekt, das abgefragt werden kann für eine "ICorDebugProcess"-Schnittstelle. Diese Methode ist veraltet in .NET Framework, Version 2.0.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppicd`  
 [out](/cpp/atl/iunknown) -Objekt, das abgefragt werden kann eine `ICorDebugProcess` Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime (CLR), das Debug-API unterstützt beschränkt prozessinternes Debuggen in .NET Framework, Version 1.0. Prozessinternes Debuggen aktiviert einen Profiler an die Inspektionsteile der Debug-API verwenden. Aufgrund von Kundenfeedback wurde prozessinternes Debuggen aus .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die mehrere im Einklang mit den die profilerstellungs-API ersetzt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Version:** 1.0  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
