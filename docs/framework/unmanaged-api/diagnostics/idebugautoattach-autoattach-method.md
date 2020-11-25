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
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720099"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** DbgAutoAttach. h  
  
## <a name="see-also"></a>Weitere Informationen

- [IDebugAutoAttach-Schnittstelle](idebugautoattach-interface.md)
