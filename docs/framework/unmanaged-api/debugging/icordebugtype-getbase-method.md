---
title: ICorDebugType::GetBase-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c24d6e9c42a091eafbe6d4bdee2bb4e055fd8852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772035"
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase-Methode
Ruft einen Schnittstellenzeiger einen ICorDebugType, der den Basistyp darstellt, sofern vorhanden, der dem Typ zugeordnet, die von diesem `ICorDebugType`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBase`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugType` -Objekt, das den Basistyp darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Suche nach der Basistyp für einen Typ ist hilfreich, die allgemeine Funktionalität für den Debugger, z. B. das ausgeben, die alle Felder eines Objekts oder die übergeordneten Klassen implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
