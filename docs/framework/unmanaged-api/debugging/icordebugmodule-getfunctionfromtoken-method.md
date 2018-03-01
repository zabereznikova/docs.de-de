---
title: ICorDebugModule::GetFunctionFromToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c449b49333de562cd5ed07f827da6bc295e9c3c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken-Methode
Ruft die Funktion, die durch das Metadatentoken angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `methodDef`  
 [in] Ein `mdMethodDef` Metadatentoken, das die Metadaten der Funktion verweist.  
  
 `ppFunction`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugFunction-Schnittstelle-Objekts, das die Funktion darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetFunctionFromToken` Methode gibt ein CORDBG_E_FUNCTION_NOT_IL HRESULT zurück, wenn der Wert übergeben `methodDef` verweist nicht auf eine Methode von Microsoft intermediate Language (MSIL).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
