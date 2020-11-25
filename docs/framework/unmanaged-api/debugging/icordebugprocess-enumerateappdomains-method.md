---
title: ICorDebugProcess::EnumerateAppDomains-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 408658a0abcba9daf4c3046476e21fd4325c7144
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695139"
---
# <a name="icordebugprocessenumerateappdomains-method"></a>ICorDebugProcess::EnumerateAppDomains-Methode

Listet alle Anwendungs Domänen in diesem Prozess auf.  
  
## <a name="syntax"></a>Syntax  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppAppDomains`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) , der ein Enumerator für die Anwendungs Domänen in diesem Prozess ist.  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode kann vor dem [ICorDebugManagedCallback::](icordebugmanagedcallback-createprocess-method.md) -Rückruf verwendet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
