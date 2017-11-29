---
title: ICorDebugModule2::SetJMCStatus-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca4b53acc69d0a56b94526de0c3b16fd1abde077
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus-Methode
Legt den Status nur mein Code (JMC) aller Methoden aller Klassen in diesem ICorDebugModule2 auf den angegebenen Wert, mit Ausnahme derjenigen in den `pTokens` -Array, das auf den entgegengesetzten Wert festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bIsJustMycode`  
 [in] Legen Sie auf `true` , wenn der Code ist andernfalls gedebuggt werden, legen Sie auf `false`.  
  
 `cTokens`  
 [in] Die Größe des `pTokens`-Arrays.  
  
 `pTokens`  
 [in] Ein Array von `mdToken` Werte, von denen jede bezieht sich auf eine Methode, deren Status "JMC" auf denen!`bIsJustMycode`.  
  
## <a name="remarks"></a>Hinweise  
 Der "JMC" Status der einzelnen Methoden, die im angegebenen der `pTokens` Array festgelegt ist, um das Gegenteil von der `bIsJustMycode` Wert. Der Status aller anderen Methoden in diesem Modul wird festgelegt, um die `bIsJustMycode` Wert.  
  
 Die `SetJMCStatus` Methode löscht alle bisherigen "JMC" Einstellungen in diesem Modul aus.  
  
 Die `SetJMCStatus` Methode gibt ein S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden. Es gibt ein HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, wenn einige Funktionen, die markiert sind `true` nicht gedebuggt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
