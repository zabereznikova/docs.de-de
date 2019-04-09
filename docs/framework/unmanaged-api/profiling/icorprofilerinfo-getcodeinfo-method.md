---
title: ICorProfilerInfo::GetCodeInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d069446ecb0b630870f0d2c9c4bdc23232c40c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120691"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>ICorProfilerInfo::GetCodeInfo-Methode
Ruft den Wertebereich des nativen Codes ab, der der angegebenen Funktions-ID zugeordnet ist.  
  
 Diese Methode ist veraltet. Verwenden der [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.  
  
 `pStart`  
 [out] Ein Zeiger auf ein Array von Bytes, aus denen sich der native Code der Funktion zusammensetzt.  
  
 `pcSize`  
 [out] Ein Zeiger auf eine ganze Zahl, die die Größe des nativen Codes in Bytes angibt.  
  
## <a name="remarks"></a>Hinweise  
 Zur Leistungsoptimierung teilt die Laufzeit in .NET Framework, Version 2.0, den vorkompilierten nativen Code einer Funktion in mehrere Bereiche auf. Daher ist die `GetCodeInfo`-Methode in .NET Framework 2.0 veraltet, weil sie den Wertebereich des systemeigenen Codes einer Funktion nicht verarbeiten kann. Profiler sollten stattdessen die allgemeinere `ICorProfilerInfo2::GetCodeInfo2`-Methode verwenden.  
  
 Diese Funktion verwendet vom Aufrufer reservierte Puffer.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.0  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
