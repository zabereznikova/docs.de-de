---
title: CorLaunchApplication-Funktion
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: e01698d2d8491b2496bb664c13dca97964cd1481
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136950"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication-Funktion
Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwClickOnceHost`  
 in Ein Wert der [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) -Enumeration, der den Typ des Hosts angibt, der die Anwendung startet.  
  
 `pwzAppFullName`  
 in Der vollständige Name der Anwendung, die gestartet wird.  
  
 `dwManifestPaths`  
 in Die Anzahl der manifestressfade für die Anwendung.  
  
 `ppwzManifestPaths`  
 in Ein Array von Zeichen folgen, von denen jede einen Pfad zu einem Manifest für die Anwendung angibt, die gestartet wird.  
  
 `dwActivationData`  
 in Die Anzahl der Aktivierungsdaten Elemente für die Anwendung, die gestartet wird.  
  
 `ppwzActivationData`  
 in Ein Array von Zeichen folgen, von denen jedes ein Aktivierungsdaten Element für die Anwendung ist, die gestartet wird.  
  
 `lpProcessInformation`  
 vorgenommen Ein Zeiger auf Informationen über den Prozess, in dem die Anwendung geladen wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
