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
ms.openlocfilehash: 5f618f6779f6931785bba18f70fb1ac9baf46753
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137189"
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

Die `GetVersion`-Methode gibt einen Fehlercode zurück, wenn keine Laufzeit in den Prozess geladen wurde.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
