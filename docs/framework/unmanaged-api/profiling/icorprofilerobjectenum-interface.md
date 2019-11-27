---
title: ICorProfilerObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: 95dce47a65bd437525011d2c1588d7e13adac85b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428183"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum-Schnittstelle
Stellt Methoden bereit, um eine Auflistung von fixierten Objekten sequenziell zu durchlaufen, die vom [Ngen. exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)generiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerObjectEnum`-Schnittstelle ab.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|Ruft die Gesamtanzahl der fixierten Objekte in der Auflistung ab.|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|Ruft die angegebene Anzahl von zusammenhängenden Objekten aus einer sequenziellen Auflistung von-Objekten ab, beginnend bei der aktuellen Position des Enumerators in der Sequenz.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.|  
|[Skip-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|Verschiebt den Cursor dieses Enumerators von seiner aktuellen Position, sodass die angegebene Anzahl von Elementen übersprungen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorProfilerObjectEnum`-Schnittstelle ist ein Enumerator. Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen. Das heißt, der Empfänger kann den Fluss von Array Elementen explizit steuern und so Probleme vermeiden, die bei der Übergabe großer Arrays als Methoden Parameter auftreten.  
  
 Verwenden Sie [ICorProfilerInfo2:: EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) zum Abrufen eines Zeigers auf die `ICorProfilerObjectEnum`-Schnittstelle.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumModuleFrozenObjects-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
