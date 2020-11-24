---
title: ICorDebugThread2::GetConnectionID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: 1507715e80761c871dfdb0b8d25dc708a2130678
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678687"
---
# <a name="icordebugthread2getconnectionid-method"></a>ICorDebugThread2::GetConnectionID-Methode

Ruft den Verbindungs Bezeichner für dieses ICorDebugThread2-Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pdwConnectionId`  
 vorgenommen Ein `CONNID` , der den Verbindungs Bezeichner darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetConnectionID` Methode gibt 0 (null) im- `pdwConnectionId` Parameter zurück, wenn dieser Thread nicht Teil einer Verbindung ist.  
  
 Wenn dieser Thread mit einer Instanz von Microsoft SQL Server 2005 Analysis Services (SSAS) verbunden ist, wird `CONNID` eine SPID (Server Process Identifier) zugeordnet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
