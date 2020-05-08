---
title: ICorDebugEval2::CreateValueForType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: fd7acaa8bcb4d53893855bcd25ff68cf26e30354
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976160"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType-Methode
Ruft einen Zeiger auf einen neuen ICorDebugValue des angegebenen Typs mit einem Anfangswert von 0 (null) oder NULL ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pType`  
 in Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.  
  
 `ppValue`  
 vorgenommen Ein `ICorDebugValue` Zeiger auf die Adresse eines Objekts, das den Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `CreateValueForType`generalisiert [ICorDebugEval:: foratevalue](icordebugeval-createvalue-method.md) , indem es Ihnen ermöglicht, einen beliebigen Objekttyp anzugeben, einschließlich `List<int>`konstruierter Typen wie. Der einzige Zweck dieser Methode besteht darin, einen Wert zu generieren, der an eine Funktions Auswertung übermittelt werden kann.  
  
 Der Typ muss eine Klasse oder ein Werttyp sein. Sie können diese Methode nicht verwenden, um Array Werte oder Zeichen folgen Werte zu erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
