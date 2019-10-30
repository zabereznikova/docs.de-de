---
title: ICorDebug::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134084"
---
# <a name="icordebuginitialize-method"></a>ICorDebug::Initialize-Methode
Initialisiert das `ICorDebug`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger muss `Initialize` zum Erstellungs Zeitpunkt aufzurufen, um die debuggingdienste zu initialisieren. Diese Methode muss aufgerufen werden, bevor eine andere Methode für `ICorDebug` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
