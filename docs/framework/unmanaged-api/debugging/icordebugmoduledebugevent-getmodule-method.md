---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709504"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>ICorDebugModuleDebugEvent::GetModule-Methode

Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppModule`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.  
  
## <a name="remarks"></a>Hinweise  

 Sie können die [geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode aufrufen, um zu bestimmen, ob das Modul geladen oder entladen wurde.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugModuleDebugEvent-Schnittstelle](icordebugmoduledebugevent-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
