---
title: ICorDebugRegisterSet2::SetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: 53660a5b10858632dffc5b31c290e9cb98d634c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712299"
---
# <a name="icordebugregisterset2setregisters-method"></a>ICorDebugRegisterSet2::SetRegisters-Methode

`SetRegisters` ist nicht in der .NET Framework Version 2,0 implementiert. Rufen Sie diese Methode nicht auf.  
  
> [!NOTE]
> Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
