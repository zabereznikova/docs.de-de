---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495255"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3-Methode

Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu. Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a>Parameter

- `ip`

  \[in] der Anweisungs Zeiger in verwaltetem Code.

- `pFunctionId`

  \[out] die Funktions-ID.

- `pReJitId`

  \[out] die Identität der neu kompilierten JIT-Version der Funktion.

## <a name="remarks"></a>Bemerkungen

Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden. Es ist eine supermenge von [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), die nur für Funktionen mit Metadaten funktioniert.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo8-Schnittstelle](icorprofilerinfo8-interface.md)
