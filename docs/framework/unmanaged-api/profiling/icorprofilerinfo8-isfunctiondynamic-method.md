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
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861735"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: isfunctiondynamic-Methode

Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a>Parameters

- `functionId`

  \[in] das `FunctionID`, das die betreffende Funktion identifiziert.

- `isDynamic`

  \[out] ein Zeiger auf eine `BOOL`, die einen Wert enthält, der angibt, ob die Funktion über keine Metadaten verfügt.

## <a name="remarks"></a>Hinweise

Eine Funktion wird als dynamisch angesehen, wenn Sie über keine Metadaten verfügt. Bestimmte Methoden wie IL-Stub-oder LCG-Methoden haben keine zugeordneten Metadaten, die mit den IMetaDataImport-APIs abgerufen werden können. Diese Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo8-Schnittstelle](icorprofilerinfo8-interface.md)
