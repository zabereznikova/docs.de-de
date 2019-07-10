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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 535d94688d02a7315529d17fae555fba457bbb86
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737871"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne.  
  
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
 [in] Die Größe des `szName`-Arrays. Legen Sie diesen Wert auf 0 (null), diese Methode in den Abfragemodus zu platzieren.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Größe der den Namen oder die Anzahl der Zeichen im tatsächlich zurückgegebenen `szName`. Im Abfragemodus kann diesen Wert den Aufrufer wissen, wie großen einen Puffer für den Namen zuweisen.  
  
 `szName`  
 [out] Ein Array, das den Namen der Anwendungsdomäne speichert.  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugger Ruft die `GetName` -Methode einmal zum Abrufen der Größe eines Puffers für den Namen erforderlich sind. Der Debugger weist den Puffer zu, und klicken Sie dann ein zweites Mal Ruft die Methode, um den Puffer zu füllen. Der erste Aufruf, zum Abrufen der Größe des Namens, wird als bezeichnet *Abfragemodus*.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
