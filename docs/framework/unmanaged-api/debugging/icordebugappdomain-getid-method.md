---
title: ICorDebugAppDomain::GetId-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0aefc19ca0c255c9c8ea40fcc12fc5cba1b00f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996254"
---
# <a name="icordebugappdomaingetid-method"></a>ICorDebugAppDomain::GetId-Methode
Ruft den eindeutigen Bezeichner der Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pId`  
 [out] Der eindeutige Bezeichner der Anwendungsdomäne.  
  
## <a name="remarks"></a>Hinweise  
 Der Bezeichner für die Anwendungsdomäne ist eindeutig innerhalb des Prozesses enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
