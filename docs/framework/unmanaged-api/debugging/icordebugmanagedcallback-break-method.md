---
title: ICorDebugManagedCallback::Break-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122582"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>ICorDebugManagedCallback::Break-Methode

Benachrichtigt den Debugger, wenn eine <xref:System.Reflection.Emit.OpCodes.Break> Anweisung im Codestream ausgeführt wird.

## <a name="syntax"></a>Syntax

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>Parameter

`pAppDomain`\
in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die Break-Anweisung enthält.

`thread`\
in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der die Break-Anweisung enthält.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
