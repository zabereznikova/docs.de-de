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
ms.openlocfilehash: df9ecc9bc355c12f993763820eb5065ba8bcc36b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855915"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3-Methode

Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu. Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a>Parameter

`ip` \
in Der Anweisungs Zeiger in verwaltetem Code.

`pFunctionId` \
vorgenommen Die Funktions-ID.

`pReJitId` \
vorgenommen Die Identität der neu kompilierten JIT-Version der Funktion.

## <a name="remarks"></a>Hinweise

Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden. Es ist eine supermenge von [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), die nur für Funktionen mit Metadaten funktioniert.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Corprof. idl, Corprof. h

**Fern** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo8-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
