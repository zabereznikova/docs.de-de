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
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976147"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction-Methode
Richtet einen Aufrufen der angegebenen ICorDebugFunction ein, die in einer Klasse geschachtelt werden kann, deren Konstruktor <xref:System.Type> Parameter annimmt, oder selbst Parameter <xref:System.Type> annehmen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein Zeiger auf ein `ICorDebugFunction` Objekt, das die aufzurufende Funktion darstellt.  
  
 `nTypeArgs`  
 in Die Anzahl von Argumenten, die von der Funktion benötigt werden.  
  
 `ppTypeArgs`  
 in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Funktions Argument darstellt.  
  
 `nArgs`  
 in Die Anzahl der in der Funktion bestandenen Werte.  
  
 `ppArgs`  
 in Ein Array von Zeigern, von denen jedes auf ein ICorDebug Value-Objekt verweist, das einen Wert darstellt, der in einem Funktions Argument übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 `CallParameterizedFunction`ist wie [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , mit dem Unterschied, dass sich die Funktion in einer Klasse mit Typparametern befinden kann, dass Sie selbst Typparameter oder beides annehmen kann. Die Typargumente sollten zuerst für die-Klasse und dann für die-Funktion angegeben werden.  
  
 Wenn sich die Funktion in einer anderen Anwendungsdomäne befindet, erfolgt ein Übergang. Alle Type-und Value-Argumente müssen sich jedoch in der Ziel Anwendungsdomäne befinden.  
  
 Die Funktions Auswertung kann nur in begrenzten Szenarios ausgeführt werden. Wenn `CallParameterizedFunction` oder `ICorDebugEval::CallFunction` fehlschlägt, gibt das zurückgegebene HRESULT den allgemeineren möglichen Grund für den Fehler an.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
