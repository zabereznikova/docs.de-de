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
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442123"
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
 in Immer auf festgelegt `GUID_NULL` .  
  
 `dwPid`  
 in Prozess-ID, die normalerweise mit der-Funktion abgerufen wird `GetCurrentProcessId` .  
  
 `dwProgramType`  
 in Programmtyp: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` oder `AUTOATTACH_PROGRAM_UNKNOWN` .  
  
 `dwProgramId`  
 in Programm-ID.  
  
 `pszSessionId`  
 in Zeichenfolge, die vom DEBUG-Verb übermittelt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** DbgAutoAttach. h  
  
## <a name="see-also"></a>Siehe auch

- [IDebugAutoAttach-Schnittstelle](idebugautoattach-interface.md)
