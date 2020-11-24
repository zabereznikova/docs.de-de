---
title: 'Icordebugvariablehome:: GetCode-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684225"
---
# <a name="icordebugvariablehomegetcode-method"></a>Icordebugvariablehome:: GetCode-Methode

Ruft die ICorDebugCode-Instanz ab, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppCode`  
 vorgenommen Ein Zeiger auf die Adresse der ICorDebugCode-Instanz, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
