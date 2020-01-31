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
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793483"
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
  
## <a name="parameters"></a>Parameters  
 `pType`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugValue` Objekts, das den Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `CreateValueForType` generalisiert [ICorDebugEval:: foratevalue](icordebugeval-createvalue-method.md) , indem es Ihnen ermöglicht, einen beliebigen Objekttyp anzugeben, einschließlich konstruierter Typen, z. b. `List<int>`. Der einzige Zweck dieser Methode besteht darin, einen Wert zu generieren, der an eine Funktions Auswertung übermittelt werden kann.  
  
 Der Typ muss eine Klasse oder ein Werttyp sein. Sie können diese Methode nicht verwenden, um Array Werte oder Zeichen folgen Werte zu erstellen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
