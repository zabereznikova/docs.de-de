---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212996"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode
Ruft die aktuellen compilerflageinstellungen ab, die von der Common Language Runtime (CLR) verwendet werden, um das richtige vorkompilierte (d. h. systemeigene) Image auszuwählen, das in diesen Prozess geladen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwFlags`  
 vorgenommen Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags-Enumerationswerte](cordebugjitcompilerflags-enumeration.md) , die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden, das geladen werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) -Methode, um die Flags festzulegen, die von der CLR verwendet werden, um das richtige vorkompilierte Image auszuwählen, das geladen werden soll.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
