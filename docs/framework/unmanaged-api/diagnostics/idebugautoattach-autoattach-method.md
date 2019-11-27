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
ms.openlocfilehash: 766aeb31436101babeab31b615a1c633578bfcc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445525"
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach-Methode
Führt eine vom Server aufgerufene automatische Debugger-Anfügung aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Wird immer auf `GUID_NULL`festgelegt.  
  
 `dwPid`  
 in Prozess-ID, die normalerweise mit der `GetCurrentProcessId`-Funktion abgerufen wird.  
  
 `dwProgramType`  
 in Programmtyp: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`oder `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 in Programm-ID.  
  
 `pszSessionId`  
 in Zeichenfolge, die vom DEBUG-Verb übermittelt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** DbgAutoAttach. h  
  
## <a name="see-also"></a>Siehe auch

- [IDebugAutoAttach-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
