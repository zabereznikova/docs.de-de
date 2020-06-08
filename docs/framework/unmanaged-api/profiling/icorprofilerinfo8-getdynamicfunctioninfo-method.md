---
title: 'ICorProfilerInfo8:: getdynamicfunctioninfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: eaf33f3b0de7a18e400cd16d29c046784e2e190f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495319"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>ICorProfilerInfo8:: getdynamicfunctioninfo-Methode

Ruft Informationen zu dynamischen Methoden ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a>Parameter

- `functionId`

  \[in] die ID der Funktion, für die Informationen abgerufen werden sollen.

- `moduleId`

  \[in] ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.

- `ppvSig`

  \[out] ein Zeiger auf die Signatur der Funktion.

- `pbSig`

  \[out] ein Zeiger auf die Anzahl von Bytes für die Funktions Signatur.

- `cchName`

  \[in] die maximale Größe des `wszName` Arrays.

- `pcchName`

  \[out] die Anzahl der Zeichen im `wszName` Array.

- `wszName`

  \[out] ein Array von `WCHAR` , bei dem es sich um den Namen der Funktion handelt, sofern vorhanden.

## <a name="remarks"></a>Bemerkungen

Bestimmte Methoden wie IL-Stub oder LCG verfügen über keine zugeordneten Metadaten, die mithilfe der APIs [IMetaDataImport](../metadata/imetadataimport-interface.md) und [IMetaDataImport2](../metadata/imetadataimport2-interface.md) abgerufen werden können. Solche Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.

Diese API kann verwendet werden, um Informationen zu dynamischen Methoden, einschließlich eines anzeigen Amens, abzurufen, falls verfügbar.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo8-Schnittstelle](icorprofilerinfo8-interface.md)
