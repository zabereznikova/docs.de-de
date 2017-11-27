---
title: CorDebugNGenPolicy-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugNGenPolicy
helpviewer_keywords: CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6042d5232995e68a4f59dfa68093446a03badfd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy-Enumeration
Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Member  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|In einem [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, die Verwendung von Bildern aus dem lokalen systemeigenen Imagecache deaktiviert ist. In einer desktop-app hat diese Einstellung keine Auswirkungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CorDebugNGENPolicy` Enumeration wird verwendet, durch die [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) Methode. Deaktivieren die Verwendung von Bildern aus dem lokalen systemeigenen Imagecache bietet eine konsistente Debugleistung erzielen, indem sichergestellt wird, dass der Debugger debugfähig JIT-kompilierten Bilder statt optimierte systemeigene Abbilder lädt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
