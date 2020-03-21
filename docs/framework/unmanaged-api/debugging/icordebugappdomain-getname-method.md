---
title: ICorDebugAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179091"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays. Legen Sie diesen Wert auf Null fest, um diese Methode in den Abfragemodus zu versetzen.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Größe des Namens oder die `szName`Anzahl der tatsächlich in zurückgegebenen Zeichen. Im Abfragemodus lässt diesen Wert den Aufrufer wissen, wie groß ein Puffer für den Namen zuzuweisen ist.  
  
 `szName`  
 [out] Ein Array, das den Namen der Anwendungsdomäne speichert.  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Debugger `GetName` ruft die Methode einmal auf, um die Größe eines Puffers abzubekommen, der für den Namen benötigt wird. Der Debugger weist den Puffer zu und ruft dann die Methode ein zweites Mal auf, um den Puffer zu füllen. Der erste Aufruf, um die Größe des Namens abzurufen, wird als *Abfragemodus*bezeichnet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
