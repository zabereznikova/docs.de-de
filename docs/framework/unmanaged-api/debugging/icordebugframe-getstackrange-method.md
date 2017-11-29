---
title: ICorDebugFrame::GetStackRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1db7617d52e07489ade339b76023e21816835ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange-Methode
Ruft den Bereich der absoluten Adresse dieses Stapelrahmens ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pStart`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Startadresse des Stapelrahmens dargestellt, die von diesem `ICorDebugFrame` Objekt.  
  
 `pEnd`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Endadresse des Stapelrahmens dargestellt, die von diesem `ICorDebugFrame` Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Adressbereich des Stapels eignet sich für die Zusammenführung überlappender stapelüberwachungen von mehreren Debugmodule gesammelt wurden. Die numerische Bereich bietet keine Informationen zum Inhalt des Stapelrahmens. Es ist sinnvoll, nur für den Vergleich der Stack-Frame-Standorten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
