---
title: ICorDebugAppDomain::IsAttached-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134674"
---
# <a name="icordebugappdomainisattached-method"></a>ICorDebugAppDomain::IsAttached-Methode
Ruft einen Wert ab, der angibt, ob der Debugger an die Anwendungsdomäne angefügt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbAttached`  
 [out] `true`, wenn der Debugger an die Anwendungsdomäne angefügt ist. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die ICorDebugController-Methoden können erst verwendet werden, wenn der Debugger an die Anwendungsdomäne angefügt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
