---
title: ICorDebugModule2::ResolveAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359691"
---
# <a name="icordebugmodule2resolveassembly-method"></a>ICorDebugModule2::ResolveAssembly-Methode

Löst die Assembly, die vom angegebenen Metadatentoken verwiesen wird.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Parameter

`tkAssemblyRef`\
[in] Ein `mdToken` -Wert, der die Assembly verweist.

`ppAssembly`\
[out] Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Assembly darstellt.

## <a name="remarks"></a>Hinweise

Wenn die Assembly bei noch nicht geladen ist `ResolveAssembly` aufgerufen wird, wird ein HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY Wert zurückgegeben.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
