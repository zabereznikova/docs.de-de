---
title: IDebugAutoAttach::AutoAttach-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b875fec2fdb6ecaeaccf8e58030b2fccbb8653b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach-Methode
AutoAttach Debuggers führt anfügen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `guidPort`  
 [in] Legen Sie immer auf `GUID_NULL`.  
  
 `dwPid`  
 [in] Prozess-ID, die normalerweise abgerufen, mit der `GetCurrentProcessId` Funktion.  
  
 `dwProgramType`  
 [in] Programmtyp: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, oder `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 [in] Programm-ID an.  
  
 `pszSessionId`  
 [in] Von der Debug-Verbs übergebene Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** DbgAutoAttach.h  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugAutoAttach-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
