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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f82303a3d38e7a5baaf1c3edcc41518228360d34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789622"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance-Funktion
Erstellt eine Instanz des angegebenen verwalteten Typs.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet. Verwenden Sie COM-Aktivierung zum Erstellen einer Instanz des verwalteten Typs oder -hosting (finden Sie unter [CLR Hosten von Schnittstellen hinzugefügt, in .NET Framework 4 und 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTypeName`  
 [in] Ein Zeiger auf den Namen des Instanztyps angefordert wird.  
  
 `riid`  
 [in] Die `IID` des Instanztyps angefordert wird.  
  
 `ppObject`  
 [out] Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, der vom Aufrufer angefordert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime sollte bereits in einen Prozess geladen werden. Sie können z. B. geladen werden, mithilfe eines Aufrufs an die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funktionieren, bevor Sie die `ClrCreateManagedInstance` Funktion wird aufgerufen. Wenn die Laufzeit nicht geladen wurde, `ClrCreateManagedInstance` versucht zuerst, Version 1.0.3705 der Laufzeit zu laden. Wenn dies fehlschlägt, versucht, die neueste Version der Laufzeit zu laden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
