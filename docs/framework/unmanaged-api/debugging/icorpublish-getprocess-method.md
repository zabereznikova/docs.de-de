---
title: ICorPublish::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178419"
---
# <a name="icorpublishgetprocess-method"></a>ICorPublish::GetProcess-Methode
Ruft eine [ICorPublishProcess-Instanz](icorpublishprocess-interface.md) ab, die den Prozess mit dem angegebenen Bezeichner darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pid`  
 [in] Der Bezeichner des Prozesses.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die `ICorPublishProcess` Adresse einer Instanz, die den Prozess darstellt.  
  
## <a name="remarks"></a>Bemerkungen  
 `GetProcess`schlägt fehl, wenn der Prozess nicht vorhanden ist oder kein verwalteter Prozess ist, der vom aktuellen Benutzer gedebuggt werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorPublish-Schnittstelle](icorpublish-interface.md)
