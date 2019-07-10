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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6b53d23410dd310766dab44664c8cd865ee9ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771686"
---
# <a name="icordebugstepper2setjmc-method"></a>ICorDebugStepper2::SetJMC-Methode
Legt einen Wert, der angibt, ob diese ICorDebugStepper nur Code verarbeitet, die von einem Anwendungsentwickler erstellt wird. Dieser Prozess wird auch bezeichnet als nur mein (JMC) Codedebuggen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fIsJMCStepper`  
 [in] Legen Sie auf `true` zum schrittweisen Durchlaufen von Code, der von einem Anwendungsentwickler erstellt wurde; andernfalls auf festgelegt ist nur `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
