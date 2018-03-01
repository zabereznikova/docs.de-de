---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode
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
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27e4693b39f9ce27ac18eb2fa542b5a0196f21cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a>ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode
Instanziiert ein neue parametrisierter Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pClass`  
 [in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts zu instanziierenden darstellt.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Typargumenten übergeben.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument für das Objekt darstellt, die instanziiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `NewParameterizedObjectNoConstructor` Methode schlägt fehl, wenn eine falsche Anzahl von Typargumenten oder die falschen Arten von Typargumenten übergeben werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
