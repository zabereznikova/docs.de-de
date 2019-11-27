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
ms.openlocfilehash: af881d23ff77f05dadbbc745b973979e35ebe9f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447569"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc-Methode

Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) zuzuordnen.

## <a name="syntax"></a>Syntax

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parameter

`cb`\
in Die Anzahl der Bytes, die für den Methoden Text zuzuordnen sind.

## <a name="remarks"></a>Hinweise

 Der zugewiesene Arbeitsspeicher beginnt bei einer Adresse, die größer ist als die Basisadresse des Moduls, das mit dieser Zuweisung verknüpft ist. Anders ausgedrückt, wird jede Zuweisung für ein bestimmtes Modul erstellt, und es wird versucht, Arbeitsspeicher in einem positiven Offset von der Basisadresse zuzuweisen. Wenn `Alloc` die angeforderte Anzahl von Bytes bei einer Adresse, die größer als die Basisadresse des Moduls ist, nicht zuordnen kann, wird unabhängig von der tatsächlich verfügbaren Speicherplatz Menge E_OUTOFMEMORY zurückgegeben.

 Die `Alloc`-Methode sollte in Verbindung mit der [ICorProfilerInfo:: abtilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) -Methode verwendet werden.

## <a name="requirements"></a>Voraussetzungen
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** CorProf.idl, CorProf.h

 **Bibliothek:** CorGuids.lib

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IMethodMalloc-Schnittstelle](imethodmalloc-interface.md)
