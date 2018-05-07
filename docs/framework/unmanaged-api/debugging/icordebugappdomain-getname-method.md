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
ms.openlocfilehash: 84f895e749fc8f2520dbce3caf9e6c11fda78a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays. Legen Sie diesen Wert auf 0 (null), um diese Methode in den Abfragemodus zu versetzen.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Größe des Namens oder die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `szName`. Im Abfragemodus kann diesen Wert den Aufrufer wissen, wie großen einen Puffer für den Namen reservieren.  
  
 `szName`  
 [out] Ein Array, das den Namen der Anwendungsdomäne speichert.  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugger Ruft die `GetName` -Methode einmal zum Abrufen der Größe eines Puffers für den Namen erforderlich sind. Der Debugger die Puffer und ruft dann die Methode ein zweites Mal auf um den Puffer zu füllen. Der erste Aufruf, zum Abrufen der Größe des Namens wird als bezeichnet *Abfragemodus*.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
