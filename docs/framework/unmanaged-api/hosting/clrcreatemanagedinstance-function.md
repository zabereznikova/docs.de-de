---
title: ClrCreateManagedInstance-Funktion
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176538"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance-Funktion
Erstellt eine Instanz des angegebenen verwalteten Typs.  
  
 Diese Funktion ist in .NET Framework 4 veraltet. Verwenden Sie die COM-Aktivierung, um eine Instanz des verwalteten Typs zu erstellen oder Das Hosting zu verwenden (siehe [CLR-Hostingschnittstellen, die in .NET Framework 4 und 4.5 hinzugefügt](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)wurden).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTypeName`  
 [in] Ein Zeiger auf den Namen des angeforderten Instanztyps.  
  
 `riid`  
 [in] Der `IID` des angeforderten Instanztyps.  
  
 `ppObject`  
 [out] Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, die vom Aufrufer angefordert wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Common Language Runtime sollte bereits in einen Prozess geladen werden. Beispielsweise kann es über einen Aufruf der [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) geladen werden, bevor die `ClrCreateManagedInstance` Funktion aufgerufen wird. Wenn die Laufzeit nicht `ClrCreateManagedInstance` geladen ist, versucht zuerst, v1.0.3705 der Laufzeit zu laden. Wenn dies fehlschlägt, wird versucht, die neueste Version der Laufzeit zu laden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
