---
title: ICorDebugStepper2::SetJMC-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 1bbcbcfbb78d421f247a13f58070b68f701e4ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697206"
---
# <a name="icordebugstepper2setjmc-method"></a>ICorDebugStepper2::SetJMC-Methode

Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde. Dieser Prozess wird auch als JMC-Debugging (Just my Code) bezeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `fIsJMCStepper`  
 in Legen Sie diese Einstellung auf fest, `true` um nur den Code zu durchlaufen, der vom Entwickler einer Anwendung erstellt wurde. andernfalls legen Sie auf fest `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
