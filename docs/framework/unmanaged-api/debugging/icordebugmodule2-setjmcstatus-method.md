---
title: ICorDebugModule2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129469"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus-Methode
Legt den nur eigenen Code (JMC)-Status aller Methoden aller Klassen in diesem ICorDebugModule2 auf den angegebenen Wert fest, mit Ausnahme derjenigen im `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIsJustMycode`  
 in Auf `true` festgelegt, wenn der Code deentschlgt werden soll. Legen Sie andernfalls auf `false`fest.  
  
 `cTokens`  
 [in] Die Größe des `pTokens`-Arrays.  
  
 `pTokens`  
 in Ein Array von `mdToken`-Werten, von denen jede auf eine Methode verweist, deren JMC-Status auf festgelegt wird.`bIsJustMycode`.  
  
## <a name="remarks"></a>Hinweise  
 Der JMC-Status jeder Methode, die im `pTokens` Array angegeben ist, wird auf das Gegenteil des `bIsJustMycode` Werts festgelegt. Der Status aller anderen Methoden in diesem Modul ist auf den `bIsJustMycode` Wert festgelegt.  
  
 Die `SetJMCStatus`-Methode löscht alle vorherigen JMC-Einstellungen in diesem Modul.  
  
 Die `SetJMCStatus`-Methode gibt ein S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden. Es wird ein CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT zurückgegeben, wenn einige Funktionen, die als `true` gekennzeichnet sind, nicht debuggt werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
