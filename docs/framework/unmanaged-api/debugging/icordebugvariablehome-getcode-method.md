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
ms.openlocfilehash: fdfa38a4cdbbaad2fc2c987a10a122af4a1fc9a9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791039"
---
# <a name="icordebugvariablehomegetcode-method"></a>Icordebugvariablehome:: GetCode-Methode
Ruft die ICorDebugCode-Instanz ab, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppCode`  
 vorgenommen Ein Zeiger auf die Adresse der ICorDebugCode-Instanz, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
