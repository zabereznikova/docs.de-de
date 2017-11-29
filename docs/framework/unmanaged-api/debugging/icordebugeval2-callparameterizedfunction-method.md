---
title: ICorDebugEval2::CallParameterizedFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 720d9c4fb9b997538ee2bb18ac7987350f6bfb57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction-Methode
Richtet einen Aufruf der angegebenen ICorDebugFunction, die innerhalb einer Klasse geschachtelt werden können, deren Konstruktor akzeptiert <xref:System.Type> akzeptieren Parameter oder kann selbst <xref:System.Type> Parameter.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pFunction`  
 [in] Ein Zeiger auf ein `ICorDebugFunction` Objekt, das die aufzurufende Funktion darstellt.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Argumenten, die die Funktion akzeptiert.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Funktionsargument für die darstellt.  
  
 `nArgs`  
 [in] Die Anzahl der Werte in der Funktion übergeben.  
  
 `ppArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugValue-Objekt verweist, die einen Wert darstellt, die an ein Funktion übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 `CallParameterizedFunction`entspricht dem [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) mit dem Unterschied, dass die Funktion innerhalb einer Klasse mit Typparametern sein kann, kann selbst dauern Typparameter oder beides. Die Typargumente müssen zuerst für die Klasse, und klicken Sie dann für die Funktion erteilt werden.  
  
 Wenn die Funktion in einer anderen Anwendungsdomäne ein Übergang erfolgen wird wird. Allerdings müssen alle Argumente von Typ und Wert in der Zielanwendungsdomäne sein.  
  
 Funktionsauswertung kann nur in bestimmten Szenarien ausgeführt werden. Wenn `CallParameterizedFunction` oder `ICorDebugEval::CallFunction` ein Fehler auftritt, das zurückgegebene HRESULT werden die allgemeinste mögliche Ursache für Fehler angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
