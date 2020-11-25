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
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721165"
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

 Der zugewiesene Arbeitsspeicher beginnt bei einer Adresse, die größer ist als die Basisadresse des Moduls, das mit dieser Zuweisung verknüpft ist. Anders ausgedrückt, wird jede Zuweisung für ein bestimmtes Modul erstellt, und es wird versucht, Arbeitsspeicher in einem positiven Offset von der Basisadresse zuzuweisen. Wenn `Alloc` die angeforderte Anzahl von Bytes bei einer Adresse, die größer als die Basisadresse des Moduls ist, nicht zuordnen kann, wird unabhängig von der tatsächlichen Menge an verfügbarem Speicherplatz E_OUTOFMEMORY zurückgegeben.

 Die- `Alloc` Methode sollte in Verbindung mit der [ICorProfilerInfo:: abtilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) -Methode verwendet werden.

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** CorProf.idl, CorProf.h

 **Bibliothek:** CorGuids.lib

 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [IMethodMalloc-Schnittstelle](imethodmalloc-interface.md)
