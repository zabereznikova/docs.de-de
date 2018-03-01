---
title: ICorDebugRegisterSet2::GetRegistersAvailable-Methode
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
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable-Methode
Ruft ein Array von Bytes, die eine Bitmap mit den verfügbaren Registern bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `numChunks`  
 [in] Die Größe des `availableRegChunks`-Arrays.  
  
 `availableRegChunks`  
 [out] Ein Array von Bytes, von denen jedes Bit eines Registers entspricht. Wenn ein Registers verfügbar ist, wird die Registrierung entsprechende Bit festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte der CorDebugRegister-Enumeration angeben die Register anderer Mikroprozessoren. Die oberen fünf Bits Anteil jedes einzelnen Werts sind der Index in der `availableRegChunks` Bytearray. Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten Byte. Erhält eine `CorDebugRegister` Wert, der angibt, ein bestimmtes Register, die Position des Registers in der Maske wird wie folgt bestimmt:  
  
1.  Extrahieren Sie Index benötigt Zugriff auf die richtige Byte in den `availableRegChunks` Array:  
  
     `CorDebugRegister`Wert >> 3  
  
2.  Extrahieren Sie die Bitposition innerhalb des indizierten Byte, in dem das niederwertigste Bit von Bit 0 (null) ist:  
  
     `CorDebugRegister`Wert & 7  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
