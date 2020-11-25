---
title: ICorProfilerInfo6-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: b3aed97e19694675fd5e0c1070dbbf6d9321eedd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733840"
---
# <a name="icorprofilerinfo6-interface"></a>ICorProfilerInfo6-Schnittstelle

[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerInfo5](icorprofilerinfo5-interface.md) , die einen Enumerator für alle Methoden bereitstellt, die in einem angegebenen ngen-Modul definiert sind, und eine bestimmte Methode Inline Inline.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Gibt einen Enumerator für alle Methoden zurück, die zu einem angegebenen ngen-Modul gehören und im Text einer angegebenen Methode Inline sind.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
