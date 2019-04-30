---
title: ICorDebugEval2::CallParameterizedFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cba4eb2b76d7057a5ed66a35342a79615cb8539f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934822"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction-Methode
Richtet einen Aufruf der angegebenen ICorDebugFunction, die innerhalb einer Klasse geschachtelt werden können, deren Konstruktor akzeptiert <xref:System.Type> dauern, Parameter und kann selbst <xref:System.Type> Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFunction`  
 [in] Ein Zeiger auf ein `ICorDebugFunction` Objekt, das die aufzurufende Funktion darstellt.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Argumenten, die die Funktion akzeptiert.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die ein Funktionsargument für die darstellt.  
  
 `nArgs`  
 [in] Die Anzahl der Werte in der Funktion übergeben.  
  
 `ppArgs`  
 [in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugValue-Objekt verweist, die einen Wert darstellt, die an eine Funktion übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 `CallParameterizedFunction` entspricht dem [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) außer die Funktion innerhalb einer Klasse mit den beiden Typparametern sein kann, selbst in Anspruch nehmen kann Typparameter oder beides. Die Typargumente sollte zuerst für die Klasse, und klicken Sie dann für die Funktion angegeben werden.  
  
 Wenn die Funktion in einer anderen Anwendungsdomäne ist, wird ein Übergang erfolgen. Allerdings müssen alle Argumente von Typ und Wert in der Zielanwendungsdomäne sein.  
  
 Die funktionsauswertung kann nur in begrenzten Szenarios ausgeführt werden. Wenn `CallParameterizedFunction` oder `ICorDebugEval::CallFunction` ein Fehler auftritt, das zurückgegebene HRESULT werden angegeben, die meisten allgemeine mögliche Ursache für Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
