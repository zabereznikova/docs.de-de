---
title: PreBindAssemblyEx-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c9bd5cb6be2ccfd25d61a8a2f4347b384e1b2567
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx-Funktion
Ruft den Anzeigenamen nach der Richtlinie für eine Assembly ab.  
  
 Diese Funktion unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAppCtx`  
 [in] Gibt den Anwendungskontext.  
  
 `pName`  
 [in] Identifiziert den Assemblynamen.  
  
 `pAsmParent`  
 [in] Identifiziert die übergeordnete Assembly. Dieser Parameter wird ignoriert.  
  
 `pwzRuntimeVersion`  
 [in] Identifiziert die Laufzeitversion an.  
  
 `ppNamePostPolicy`  
 [out] Enthält den Anzeigenamen nach der Richtlinie an.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`ein null-Verweis muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `ppNamePostPolicy` Output-Parameter festgelegt ist, nur, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt. Es ist, andernfalls null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Fusionsfunktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
