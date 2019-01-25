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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f2a05009caed7bef6da9edee57a4a54b876b18f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580992"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication-Funktion
Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `dwClickOnceHost`  
 [in] Der Wert der [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) -Enumeration, der den Typ des Hosts gibt an, die die Anwendung gestartet wird.  
  
 `pwzAppFullName`  
 [in] Der vollständige Name der Anwendung, die gestartet wird.  
  
 `dwManifestPaths`  
 [in] Die Anzahl der Manifestspfade für die Anwendung.  
  
 `ppwzManifestPaths`  
 [in] Ein Array von Zeichenfolgen, von denen jede einen Pfad zu einem Anwendungsmanifest für die Anwendung angibt, das gestartet wird.  
  
 `dwActivationData`  
 [in] Die Anzahl der Aktivierung von Datenelementen für die Anwendung, die gestartet wird.  
  
 `ppwzActivationData`  
 [in] Ein Array von Zeichenfolgen, von denen jede eine Aktivierung-Datenelement für die Anwendung ist, das gestartet wird.  
  
 `lpProcessInformation`  
 [out] Ein Zeiger auf die Informationen über den Prozess, in dem die Anwendung geladen wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
