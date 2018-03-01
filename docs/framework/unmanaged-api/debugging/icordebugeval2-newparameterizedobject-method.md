---
title: ICorDebugEval2::NewParameterizedObject-Methode
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
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 39b69a82f25ab6df5f2bd2f6dc70caf1bf13a0f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a>ICorDebugEval2::NewParameterizedObject-Methode
Instanziiert ein neue parametrisierter Typ-Objekt, und die Konstruktormethode des Objekts aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pConstructor`  
 [in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das den Konstruktor des Objekts zu instanziierenden darstellt.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Typargumenten übergeben.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument für das Objekt darstellt, die instanziiert wird.  
  
 `nArgs`  
 [in] Die Anzahl von Argumenten an den Konstruktor übergeben.  
  
 `ppArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugValue-Objekt verweist, die einen Wert des Arguments darstellt, der an den Konstruktor übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor des Objekts dauert <xref:System.Type> Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
