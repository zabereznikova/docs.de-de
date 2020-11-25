---
title: ICorDebugFrame::GetStackRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 0cfc734e3c2d250bba045a926f5b178b6cbc1ba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728198"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange-Methode

Ruft den absoluten Adressbereich dieses Stapel Rahmens ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pStart`  
 vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` , der die Startadresse des Stapel Rahmens angibt, der durch dieses-Objekt dargestellt wird `ICorDebugFrame` .  
  
 `pEnd`  
 vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` , der die Endadresse des Stapel Rahmens angibt, der durch dieses-Objekt dargestellt wird `ICorDebugFrame` .  
  
## <a name="remarks"></a>Hinweise  

 Der Adressbereich des Stapels eignet sich für die Zusammenfassung von verschachtelten Stapel Überwachungen, die von mehreren Debugmodulen gesammelt werden. Der numerische Bereich enthält keine Informationen über den Inhalt des Stapel Rahmens. Dies ist nur für den Vergleich von Stapel Rahmen Standorten sinnvoll.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
