---
title: ICorDebugModule::GetFunctionFromToken-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: bf2acd897c9c45e445b864f85550ed7ed6e00886
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710154"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken-Methode

Ruft die Funktion ab, die vom Metadatentoken angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `methodDef`  
 in Ein `mdMethodDef` Metadatentoken, das auf die Metadaten der Funktion verweist.  
  
 `ppFunction`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug Function-Schnittstellen Objekts, das die Funktion darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetFunctionFromToken` Methode gibt einen CORDBG_E_FUNCTION_NOT_IL HRESULT zurück, wenn der übergebenen Wert `methodDef` nicht auf eine MSIL-Methode (Microsoft Intermediate Language) verweist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
