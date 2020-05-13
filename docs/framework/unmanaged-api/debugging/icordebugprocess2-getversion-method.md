---
title: ICorDebugProcess2::GetVersion-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213503"
---
# <a name="icordebugprocess2getversion-method"></a>ICorDebugProcess2::GetVersion-Methode

Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die in diesem Prozess ausgeführt wird.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a>Parameter

`version`\
vorgenommen Ein Zeiger auf eine COR_VERSION-Struktur, die die Versionsnummer der Laufzeit speichert.

## <a name="remarks"></a>Hinweise

Die- `GetVersion` Methode gibt einen Fehlercode zurück, wenn keine Laufzeit in den Prozess geladen wurde.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
