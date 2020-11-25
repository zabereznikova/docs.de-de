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
ms.openlocfilehash: ca427439f03d92b20e7714b9724d90b240e9cecb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704070"
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
 in Ein Wert der [HOST_TYPE](host-type-enumeration.md) -Enumeration, die den Typ des Hosts angibt, der die Anwendung startet.  
  
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
