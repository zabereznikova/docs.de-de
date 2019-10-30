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
ms.openlocfilehash: b27e7a2cdcbfc3a88a734230118d99c2dd5c700e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129535"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName-Methode
Ruft den Dateinamen des Moduls ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchname`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 in Ein Zeiger auf die Länge des zurückgegebenen Namens.  
  
 `szName`  
 vorgenommen Ein Array, in dem der zurückgegebene Name gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetName`-Methode gibt ein S_OK HRESULT zurück, wenn der Dateiname des Moduls mit dem Namen auf dem Datenträger übereinstimmt. `GetName` gibt ein S_FALSE HRESULT zurück, wenn der Name erstellt wird, z. b. für ein dynamisches Modul oder ein in-Memory-Modul.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
