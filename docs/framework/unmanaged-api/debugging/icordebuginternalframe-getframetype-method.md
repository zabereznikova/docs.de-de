---
title: ICorDebugInternalFrame::GetFrameType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7e5fceacc3fefa9267a9d7f989e745c392322e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414124"
---
# <a name="icordebuginternalframegetframetype-method"></a>ICorDebugInternalFrame::GetFrameType-Methode
Ruft den Typ dieses interne Rahmens ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pType`  
 [out] Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ des internen Frames dargestellt, die von diesem angibt `ICorDebugInternalFrame` Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der interne Rahmentyp wird nie STUBFRAME_NONE. Debugger sollten nicht erkannte interne Rahmentypen ordnungsgemäß ignorieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
