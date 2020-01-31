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
ms.openlocfilehash: 015735e1c6c3b6c146f2fca3a9bdc28baeca2f92
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792522"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode
Ruft die aktuellen compilerflageinstellungen ab, die von der Common Language Runtime (CLR) verwendet werden, um das richtige vorkompilierte (d. h. systemeigene) Image auszuwählen, das in diesen Prozess geladen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pdwFlags`  
 vorgenommen Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags-Enumerationswerte](cordebugjitcompilerflags-enumeration.md) , die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden, das geladen werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) -Methode, um die Flags festzulegen, die von der CLR verwendet werden, um das richtige vorkompilierte Image auszuwählen, das geladen werden soll.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
