---
title: ICorDebugRegisterSet::SetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: eba86c09197aad6bac284c52fe164432e197c6f7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378250"
---
# <a name="icordebugregistersetsetregisters-method"></a>ICorDebugRegisterSet::SetRegisters-Methode
`SetRegisters`ist nicht in der .NET Framework Version 2,0 implementiert. Rufen Sie diese Methode nicht auf.  
  
> [!NOTE]
> Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
