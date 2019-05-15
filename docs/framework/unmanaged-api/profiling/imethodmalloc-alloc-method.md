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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66bd56a332dc34fd35f3129256cc0e3d6c5d4508
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636703"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc-Methode

Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf zu reservieren.

## <a name="syntax"></a>Syntax

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parameter

`cb`\
[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.

## <a name="remarks"></a>Hinweise

 Der zugeordnete Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das mit dieser Zuordnung verknüpft ist. Das heißt, jede Zuweisung für ein bestimmtes Modul erstellt wird, und versucht, aus der Basisadresse mit einem positiven Offset speicherbelegung. Wenn `Alloc` nicht die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls kann unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.

 Die `Alloc` Methode sollte verwendet werden, in Verbindung mit der [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) Methode.

## <a name="requirements"></a>Anforderungen
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** CorProf.idl, CorProf.h

 **Bibliothek:** CorGuids.lib

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IMethodMalloc-Schnittstelle](imethodmalloc-interface.md)
