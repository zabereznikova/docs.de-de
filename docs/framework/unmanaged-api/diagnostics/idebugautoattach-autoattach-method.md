---
title: IDebugAutoAttach::AutoAttach-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077133"
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
  
## <a name="parameters"></a>Parameter  
 `guidPort`  
 [in] Legen Sie immer auf `GUID_NULL`.  
  
 `dwPid`  
 [in] Prozess-ID, die normalerweise mit abgerufen. die `GetCurrentProcessId` Funktion.  
  
 `dwProgramType`  
 [in] Programmtyp: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, oder `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 [in] Programm-ID an.  
  
 `pszSessionId`  
 [in] Zeichenfolge, die durch das Debug-Verb übergeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** DbgAutoAttach.h  
  
## <a name="see-also"></a>Siehe auch

- [IDebugAutoAttach-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
