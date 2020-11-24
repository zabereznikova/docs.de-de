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
ms.openlocfilehash: 967f8f25e240f484ae86852c740be12cd3a6409e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681820"
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase-Methode

Ruft einen Schnittstellen Zeiger auf einen ICorDebugType ab, der den Basistyp des Typs darstellt, der von diesem dargestellt wird `ICorDebugType` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pBase`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den Basistyp darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Das Suchen des Basistyps für einen Typ ist nützlich, um allgemeine Debuggerfunktionen zu implementieren, wie z. b. das Drucken aller Felder eines Objekts oder der übergeordneten Klassen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
