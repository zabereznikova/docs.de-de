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
ms.openlocfilehash: d5109043a8601d7997f52e88ea472644f1b9ca03
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208784"
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
 in Legen Sie auf fest, `true` Wenn der Code deentschlgt werden soll, und legen Sie andernfalls auf fest `false` .  
  
 `cTokens`  
 [in] Die Größe des `pTokens`-Arrays.  
  
 `pTokens`  
 in Ein Array von- `mdToken` Werten, von denen jede auf eine Methode verweist, deren JMC-Status auf! festgelegt wird `bIsJustMycode` .  
  
## <a name="remarks"></a>Hinweise  
 Der JMC-Status jeder Methode, die im-Array angegeben ist, `pTokens` wird auf das Gegenteil des-Werts festgelegt `bIsJustMycode` . Der Status aller anderen Methoden in diesem Modul wird auf den Wert festgelegt `bIsJustMycode` .  
  
 Die- `SetJMCStatus` Methode löscht alle vorherigen JMC-Einstellungen in diesem Modul.  
  
 Die- `SetJMCStatus` Methode gibt eine S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden. Es wird ein CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT zurückgegeben, wenn einige Funktionen, die markiert sind, `true` nicht debuggt werden können.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
