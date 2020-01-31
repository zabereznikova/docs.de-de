---
title: ICorProfilerInfo2::GetBoxClassLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862827"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>ICorProfilerInfo2::GetBoxClassLayout-Methode
Ruft Informationen darüber ab, wo sich der angegebene Werttyp befindet, wenn er gekapselt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parameters  
 `classId`  
 in Die ID der Klasse, die den zu boachtelten Werttyp beschreibt.  
  
 `pBufferOffset`  
 vorgenommen Eine ganze Zahl, die den Offset des Werttyps relativ zum Objekt-ID-Zeiger des Objekts ist.  
  
## <a name="remarks"></a>Hinweise  
 Der `pBufferOffset` Wert ist der Speicherort des Werttyps in einem Feld. Nachdem `pBufferOffset` auf ein geachteltes Objekt angewendet wurde, kann das Klassen Layout des Werttyps verwendet werden, um den Wert des Objekts zu interpretieren.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
