---
title: ICorDebugProcess::GetHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695061"
---
# <a name="icordebugprocessgethandle-method"></a>ICorDebugProcess::GetHandle-Methode

Ruft ein Handle für den Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a>Parameter  

 `phProcessHandle`  
 vorgenommen Ein Zeiger auf einen `HPROCESS` , der das Handle für den Prozess ist.  
  
## <a name="remarks"></a>Hinweise  

 Der Besitzer des abgerufenen Handles ist die Debugschnittstelle. Der Debugger sollte das Handle vor der Verwendung duplizieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
