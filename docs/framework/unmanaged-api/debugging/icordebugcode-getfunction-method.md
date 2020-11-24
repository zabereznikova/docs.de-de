---
title: ICorDebugCode::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 99972c5840645c95b7b349daf2d8ea7173d0cc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674723"
---
# <a name="icordebugcodegetfunction-method"></a>ICorDebugCode::GetFunction-Methode

Ruft den "ICorDebugFunction" ab, der diesem "ICorDebugCode" zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppFunction`  
 vorgenommen Ein Zeiger auf die Adresse der Funktion.  
  
## <a name="remarks"></a>Hinweise  

 `ICorDebugCode` und `ICorDebugFunction` pflegen eine 1:1-Beziehung.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
