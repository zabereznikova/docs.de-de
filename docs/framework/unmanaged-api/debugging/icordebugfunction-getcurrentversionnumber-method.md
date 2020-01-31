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
ms.openlocfilehash: 5e080e9aa89816b24aa2eb1b6b1be823922e86fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794522"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>ICorDebugFunction::GetCurrentVersionNumber-Methode
Ruft die Versionsnummer der letzten Bearbeitung der Funktion ab, die von diesem ICorDebugFunction-Objekt dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pnCurrentVersion`  
 vorgenommen Ein Zeiger auf einen ganzzahligen Wert, der die Versionsnummer der letzten Bearbeitung ist, die an dieser Funktion vorgenommen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Versionsnummer der aktuellen Bearbeitung, die an dieser Funktion vorgenommen wurde, ist möglicherweise größer als die Versionsnummer der Funktion selbst. Verwenden Sie entweder die [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) -Methode oder die [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) -Methode, um die Versionsnummer der Funktion abzurufen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
