---
title: ICorDebugAppDomain2::GetFunctionPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: be797b1b3f288fd367d7f624e9cf33015dd114ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698272"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a>ICorDebugAppDomain2::GetFunctionPointerType-Methode

Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `nTypeArgs`  
 in Die Anzahl der Typargumente für die Funktion.  
  
 `ppTypeArgs`  
 in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Typargument der Funktion darstellt. Das erste Element ist der Rückgabetyp. Jedes der anderen Elemente ist ein Parametertyp.  
  
 `ppType`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den Zeiger auf die Funktion darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
