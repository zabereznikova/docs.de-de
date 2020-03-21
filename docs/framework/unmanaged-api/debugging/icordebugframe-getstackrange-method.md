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
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178900"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange-Methode
Ruft den absoluten Adressbereich dieses Stapelrahmens ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pStart`  
 [out] Ein Zeiger auf `CORDB_ADDRESS` ein, der die Startadresse des `ICorDebugFrame` Stapelrahmens angibt, der durch dieses Objekt dargestellt wird.  
  
 `pEnd`  
 [out] Ein Zeiger auf `CORDB_ADDRESS` ein, der die Endadresse des `ICorDebugFrame` Stapelrahmens angibt, der durch dieses Objekt dargestellt wird.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Adressbereich des Stapels ist nützlich, um übereinandergelegte Stapelablaufverfolgungen, die von mehreren Debugging-Engines gesammelt wurden, zusammenzufügen. Der numerische Bereich enthält keine Informationen über den Inhalt des Stapelrahmens. Es ist nur für den Vergleich von Stapelrahmenpositionen sinnvoll.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
