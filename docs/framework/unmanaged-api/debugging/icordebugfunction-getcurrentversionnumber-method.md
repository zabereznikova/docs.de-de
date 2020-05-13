---
title: ICorDebugFunction::GetCurrentVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212905"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>ICorDebugFunction::GetCurrentVersionNumber-Methode
Ruft die Versionsnummer der letzten Bearbeitung der Funktion ab, die von diesem ICorDebugFunction-Objekt dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnCurrentVersion`  
 vorgenommen Ein Zeiger auf einen ganzzahligen Wert, der die Versionsnummer der letzten Bearbeitung ist, die an dieser Funktion vorgenommen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Versionsnummer der aktuellen Bearbeitung, die an dieser Funktion vorgenommen wurde, ist möglicherweise größer als die Versionsnummer der Funktion selbst. Verwenden Sie entweder die [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) -Methode oder die [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) -Methode, um die Versionsnummer der Funktion abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
