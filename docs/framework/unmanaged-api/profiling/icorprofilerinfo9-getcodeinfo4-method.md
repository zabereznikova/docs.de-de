---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3e3e3afc221d153ff3573126ff10014d39af761a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868303"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9:: GetCodeInfo4-Methode

Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a>Parameters

- `pNativeCodeStartAddress`

  \[in] ein Zeiger auf den Anfang einer nativen Funktion.

- `cCodeInfos`

  \[in] die Größe des `codeInfos` Arrays.

- `pcCodeInfos`

  \[out] ein Zeiger auf die Gesamtzahl der verfügbaren [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen.

- `codeInfos`

  \[out] ein vom Aufrufer bereitgestellter Puffer. Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.

## <a name="remarks"></a>Hinweise

Die `GetCodeInfo4`-Methode ähnelt [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), mit der Ausnahme, dass Sie Code Informationen für verschiedene Native Versionen einer Methode suchen kann.

> [!NOTE]
> `GetCodeInfo4` können eine Garbage Collection auslöst.

Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.

Nachdem `GetCodeInfo4` zurückgegeben hat, müssen Sie überprüfen, ob der `codeInfos` Puffer groß genug war, um alle [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen zu enthalten. Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters. Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Struktur kleiner als `pcCodeInfos`ist, weisen Sie einen größeren `codeInfos` Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen, größeren Größe, und wenden Sie `GetCodeInfo4` erneut an.

Alternativ können Sie zuerst `GetCodeInfo4` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können dann die `codeInfos` Puffergröße auf den Wert festlegen, der in `pcCodeInfos`zurückgegeben wurde, multipliziert mit der Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Struktur, und `GetCodeInfo4` erneut aufzurufen.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo9-Schnittstelle](ICorProfilerInfo9-interface.md)
