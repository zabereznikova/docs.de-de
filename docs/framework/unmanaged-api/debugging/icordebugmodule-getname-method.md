---
title: ICorDebugModule::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bebee019595143d25e950719ad62d9e10b76a3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName-Methode
Ruft den Dateinamen des Moduls ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchname`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 [in] Ein Zeiger auf die Länge des zurückgegebenen Namen.  
  
 `szName`  
 [out] Ein Array, das den zurückgegebenen Namen speichert.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetName` Methode gibt ein S_OK HRESULT aus, wenn der Dateiname für das Modul mit dem Namen auf dem Datenträger übereinstimmt. `GetName` Gibt HRESULT "S_FALSE" zurück, wenn der Name, erstellt wurde, z. B. für ein dynamisches oder in-Memory-Modul ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
 
