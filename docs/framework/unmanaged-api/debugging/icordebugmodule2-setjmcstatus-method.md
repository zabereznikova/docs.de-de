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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d20c640d6a6a43b7bde4c7d46df470c7bc8c5aa2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499523"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus-Methode
Legt den Zustand nur mein Code (JMC) alle Methoden von der alle Klassen, die in dieses ICorDebugModule2 auf den angegebenen Wert, mit Ausnahme derjenigen in der `pTokens` Array, das auf den entgegengesetzten Wert festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIsJustMycode`  
 [in] Legen Sie auf `true` , wenn der Code ist, werden andernfalls debuggten, legen Sie auf `false`.  
  
 `cTokens`  
 [in] Die Größe des `pTokens`-Arrays.  
  
 `pTokens`  
 [in] Ein Array von `mdToken` Werte, von denen jede bezieht sich auf eine Methode, die den JMC Status hat!`bIsJustMycode`.  
  
## <a name="remarks"></a>Hinweise  
 Die JMC Status jeder einzelnen Methode, die im angegebenen die `pTokens` Array festgelegt ist, auf das Gegenteil von der `bIsJustMycode` Wert. Der Status aller anderen Methoden in diesem Modul wird festgelegt, um die `bIsJustMycode` Wert.  
  
 Die `SetJMCStatus` Methode löscht alle vorherige JMC-Einstellungen in diesem Modul.  
  
 Die `SetJMCStatus` Methode gibt ein S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden. Gibt ein HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, wenn einige Funktionen, die markiert sind `true` nicht debuggt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
