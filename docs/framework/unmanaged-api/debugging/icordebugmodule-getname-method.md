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
ms.openlocfilehash: c2aecadf8688e763a69bd40ca877e44bc0ce5c29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710033"
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

 Die `GetName` -Methode gibt eine S_OK HRESULT zurück, wenn der Dateiname des Moduls mit dem Namen auf dem Datenträger übereinstimmt. `GetName` gibt eine S_FALSE HRESULT zurück, wenn der Name erfunden ist, z. b. für ein dynamisches Modul oder ein in-Memory-Modul.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
