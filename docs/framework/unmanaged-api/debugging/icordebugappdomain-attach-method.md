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
ms.openlocfilehash: d133cacb611a1c7bd03d7653f46c2e5fb1acc043
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723349"
---
# <a name="icordebugappdomainattach-method"></a>ICorDebugAppDomain::Attach-Methode

Fügt den Debugger an die Anwendungsdomäne an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger muss an die Anwendungsdomäne angefügt werden, um Ereignisse zu empfangen und das Debuggen der Anwendungsdomäne zu ermöglichen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
