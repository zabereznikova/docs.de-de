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
ms.openlocfilehash: 828e4dc67cb93d0a35879e94b54c9fac6e5bda16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124085"
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
 vorgenommen Ein Zeiger auf eine `CORDB_ADDRESS`, die die Startadresse des Stapel Rahmens angibt, der durch dieses `ICorDebugFrame`-Objekt dargestellt wird.  
  
 `pEnd`  
 vorgenommen Ein Zeiger auf eine `CORDB_ADDRESS`, die die Endadresse des Stapel Rahmens angibt, der durch dieses `ICorDebugFrame`-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Adressbereich des Stapels eignet sich für die Zusammenfassung von verschachtelten Stapel Überwachungen, die von mehreren Debugmodulen gesammelt werden. Der numerische Bereich enthält keine Informationen über den Inhalt des Stapel Rahmens. Dies ist nur für den Vergleich von Stapel Rahmen Standorten sinnvoll.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
