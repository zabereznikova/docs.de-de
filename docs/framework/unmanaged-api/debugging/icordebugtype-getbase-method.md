---
title: ICorDebugType::GetBase-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c28c88988155cf5e00897858d4306e4cb2ea78a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase-Methode
Ruft einen Schnittstellenzeiger einen ICorDebugType, der den Basistyp darstellt, sofern vorhanden, der der Typ des von diesem dargestellt `ICorDebugType`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBase`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das den Basistyp darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Basistyp für einen Typ Nachschlagen ist nützlich, allgemeine Debuggerfunktionen, z. B. Ausgeben aller Felder eines Objekts oder die übergeordneten Klassen implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
