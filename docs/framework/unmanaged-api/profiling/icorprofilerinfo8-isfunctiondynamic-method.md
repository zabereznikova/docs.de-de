---
title: 'ICorProfilerInfo8:: isfunctiondynamic'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 01aa1df27dccf41060083333588e04bc5ea88520
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855925"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: isfunctiondynamic-Methode

Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a>Parameter

`functionId` \
in  Der `FunctionID` , der die betreffende Funktion identifiziert.

`isDynamic` \
vorgenommen Ein Zeiger auf einen `BOOL` , der einen Wert enthält, der angibt, ob die Funktion über keine Metadaten verfügt.

## <a name="remarks"></a>Hinweise

Eine Funktion wird als dynamisch angesehen, wenn Sie über keine Metadaten verfügt. Bestimmte Methoden wie IL-Stub-oder LCG-Methoden haben keine zugeordneten Metadaten, die mit den IMetaDataImport-APIs abgerufen werden können. Diese Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Corprof. idl, Corprof. h

**Fern** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo8-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
