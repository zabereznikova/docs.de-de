---
title: ICorDebugAppDomain::Attach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 66ec64b1a855a3d31f14f3ef29dde0b82361f5d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133985"
---
# <a name="icordebugappdomainattach-method"></a>ICorDebugAppDomain::Attach-Methode
Fügt den Debugger an die Anwendungsdomäne an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger muss an die Anwendungsdomäne angefügt werden, um Ereignisse zu empfangen und das Debuggen der Anwendungsdomäne zu ermöglichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
