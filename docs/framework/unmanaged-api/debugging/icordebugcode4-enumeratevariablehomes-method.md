---
title: ICorDebugCode4::EnumerateVariableHomes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f55675bf79b98a7af47f6bec561704a4e5dd565
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486107"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>ICorDebugCode4::EnumerateVariableHomes-Methode
Ruft einen Enumerator auf das lokale Variablen und Argumente in einer Funktion ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
 Ein Zeiger auf die Adresse einer [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) Schnittstellenobjekts, das einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellenobjekt wird einen Standardenumerator, die von der "ICorDebugEnum"-Schnittstelle, die Sie zum Aufzählen kann abgeleitet [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte. Fügen Sie die Auflistung kann mehrere [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte für den Slot oder das Argument Index ggf. verschiedene Häuser an verschiedenen Punkten in der Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugCode4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
