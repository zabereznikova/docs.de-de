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
ms.openlocfilehash: fce89cc2b3b0104ba017b7df9105dea3f6ec4e91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868225"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum-Schnittstelle
Stellt Methoden bereit, um eine Auflistung von fixierten Objekten sequenziell zu durchlaufen, die vom [Ngen. exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)generiert werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](icorprofilerobjectenum-clone-method.md)|Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerObjectEnum`-Schnittstelle ab.|  
|[GetCount-Methode](icorprofilerobjectenum-getcount-method.md)|Ruft die Gesamtanzahl der fixierten Objekte in der Auflistung ab.|  
|[Next-Methode](icorprofilerobjectenum-next-method.md)|Ruft die angegebene Anzahl von zusammenhängenden Objekten aus einer sequenziellen Auflistung von-Objekten ab, beginnend bei der aktuellen Position des Enumerators in der Sequenz.|  
|[Reset-Methode](icorprofilerobjectenum-reset-method.md)|Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.|  
|[Skip-Methode](icorprofilerobjectenum-skip-method.md)|Verschiebt den Cursor dieses Enumerators von seiner aktuellen Position, sodass die angegebene Anzahl von Elementen übersprungen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorProfilerObjectEnum`-Schnittstelle ist ein Enumerator. Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen. Das heißt, der Empfänger kann den Fluss von Array Elementen explizit steuern und so Probleme vermeiden, die bei der Übergabe großer Arrays als Methoden Parameter auftreten.  
  
 Verwenden Sie [ICorProfilerInfo2:: EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md) zum Abrufen eines Zeigers auf die `ICorProfilerObjectEnum`-Schnittstelle.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [EnumModuleFrozenObjects-Methode](icorprofilerinfo2-enummodulefrozenobjects-method.md)
