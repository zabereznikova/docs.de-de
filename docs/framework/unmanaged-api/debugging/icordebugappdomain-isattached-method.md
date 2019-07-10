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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a3f01edcd6ce1d16ab2c651a66d2fd9cd2eb0ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737817"
---
# <a name="icordebugappdomainisattached-method"></a>ICorDebugAppDomain::IsAttached-Methode
Ruft einen Wert, der angibt, ob die Anwendungsdomäne der Debugger angefügt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbAttached`  
 [out] `true` ist der Debugger an die Anwendungsdomäne angefügt ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die ICorDebugController-Methoden können nicht verwendet werden, bis der Debugger an die Anwendungsdomäne angefügt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
