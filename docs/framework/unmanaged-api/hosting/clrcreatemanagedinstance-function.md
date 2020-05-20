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
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616813"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance-Funktion
Erstellt eine Instanz des angegebenen verwalteten Typs.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert. Verwenden Sie die COM-Aktivierung, um eine Instanz des verwalteten Typs zu erstellen, oder verwenden Sie das Hosting (siehe [CLR-Hostingschnittstellen, die im .NET Framework 4 und 4,5 hinzugefügt](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)wurden)  
  
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
 in Ein Zeiger auf den Namen des angeforderten Instanztyps.  
  
 `riid`  
 in Der `IID` des angefragten Instanztyps.  
  
 `ppObject`  
 vorgenommen Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, der vom Aufrufer angefordert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime sollte bereits in einen Prozess geladen werden. Beispielsweise kann Sie mithilfe eines Aufrufs der [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion geladen werden, bevor die- `ClrCreateManagedInstance` Funktion aufgerufen wird. Wenn die Laufzeit nicht geladen ist, `ClrCreateManagedInstance` versucht zuerst, die v-1.0.3705 der Laufzeit zu laden. Wenn dies nicht möglich ist, wird versucht, die neueste Version der Laufzeit zu laden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
- [Hosting](index.md)
