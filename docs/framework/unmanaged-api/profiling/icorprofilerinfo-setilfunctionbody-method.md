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
ms.openlocfilehash: da81bd3e255898543c94d4ac64c6afbf39b6bdba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449882"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody-Methode
Ersetzt den Text der angegebenen Funktion im angegebenen Modul.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Die ID des Moduls, in dem sich die Funktion befindet.  
  
 `methodid`  
 in Das Token der Funktion, für die der Text ersetzt werden soll.  
  
 `pbNewILMethodHeader`  
 in Der neue Header für die Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetILFunctionBody`-Methode ersetzt die relative virtuelle Adresse der Funktion in den Metadaten, sodass Sie auf den neuen Funktions Text verweist, und passt alle internen Datenstrukturen nach Bedarf an.  
  
 Die `SetILFunctionBody`-Methode kann nur für die Funktionen aufgerufen werden, die noch nie von einem JIT-Compiler (Just-in-Time) kompiliert wurden.  
  
 Verwenden Sie die [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) -Methode, um Speicherplatz für die neue Methode zuzuweisen, um sicherzustellen, dass der Puffer kompatibel ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
