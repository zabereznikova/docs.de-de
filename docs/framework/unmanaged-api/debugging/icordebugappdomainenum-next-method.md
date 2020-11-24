---
title: ICorDebugAppDomainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: b315f38dc306727e33b52b84d17951a91ccdc39f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684472"
---
# <a name="icordebugappdomainenumnext-method"></a>ICorDebugAppDomainEnum::Next-Methode

Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `celt`  
 in Die Anzahl der Anwendungs Domänen, die abgerufen werden sollen.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebugAppDomain-Objekt verweist, das eine Anwendungsdomäne darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen. Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
