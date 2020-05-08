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
ms.openlocfilehash: a2f6df7647ffe9f2adff963b6629ed29ece053c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895162"
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
 vorgenommen `true` , wenn der Debugger an die Anwendungsdomäne angefügt ist. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die ICorDebugController-Methoden können erst verwendet werden, wenn der Debugger an die Anwendungsdomäne angefügt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
