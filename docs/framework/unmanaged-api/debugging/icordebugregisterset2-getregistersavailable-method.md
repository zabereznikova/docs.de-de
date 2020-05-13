---
title: ICorDebugRegisterSet2::GetRegistersAvailable-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378222"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable-Methode
Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `numChunks`  
 [in] Die Größe des `availableRegChunks`-Arrays.  
  
 `availableRegChunks`  
 vorgenommen Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht. Wenn ein Register verfügbar ist, wird das entsprechende Bit des Registrierungs Satzes festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte der CorDebugRegister-Enumeration geben die Register verschiedener Mikroprozessoren an. Die oberen fünf Bits der einzelnen Werte sind der Index im `availableRegChunks` Bytearray. Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten bytes. Wenn ein `CorDebugRegister` Wert angegeben ist, der ein bestimmtes Register angibt, wird die Position des Registers in der Maske wie folgt bestimmt:  
  
1. Extrahieren Sie den Index, der für den Zugriff auf das richtige Byte im Array erforderlich ist `availableRegChunks` :  
  
     `CorDebugRegister`Wert >> 3  
  
2. Extrahieren Sie die Bitposition innerhalb des indizierten bytes, wobei Bit NULL das am wenigsten bedeutende Bit ist:  
  
     `CorDebugRegister`Wert & 7  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
