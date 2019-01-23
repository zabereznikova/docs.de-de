---
title: ICorProfilerInfo::SetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff79f6e439f2bafd598d9d416cc6f7404f4c231d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547331"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody-Methode
Ersetzt den Text der angegebenen Funktion im angegebenen Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, in dem die Funktion befindet.  
  
 `methodid`  
 [in] Das Token der Funktion für den Text ersetzt werden soll.  
  
 `pbNewILMethodHeader`  
 [in] Der neue Header für die Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetILFunctionBody` Methode ersetzt die relative virtuelle Adresse der Funktion in den Metadaten, sodass er auf den Hauptteil der neuen Funktion verweist, und alle internen Datenstrukturen nach Bedarf angepasst.  
  
 Die `SetILFunctionBody` Methode kann aufgerufen werden, nur für Funktionen, die nie von einem just-in-Time (JIT)-Compiler kompiliert wurden.  
  
 Verwenden der [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) Methode zum Zuweisen von Speicherplatz für die neue Methode, um sicherzustellen, dass der Puffer kompatibel ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
