---
title: ICorDebugEval2::NewParameterizedObject-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c35baaee13782566c64dd8447c6a034f699b5cd0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479609"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>ICorDebugEval2::NewParameterizedObject-Methode
Instanziiert ein neues Objekt für den parametrisierten Typ und die Konstruktormethode des Objekts aufgerufen.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pConstructor`  
 [in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das den Konstruktor des Objekts zu instanziierenden darstellt.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Typargumenten übergeben.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die ein Typargument für das Objekt darstellt, die instanziiert wird.  
  
 `nArgs`  
 [in] Die Anzahl von Argumenten, die an den Konstruktor übergeben werden.  
  
 `ppArgs`  
 [in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugValue-Objekt verweist, die einen Wert des Arguments darstellt, der an den Konstruktor übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor des Objekts dauert <xref:System.Type> Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
