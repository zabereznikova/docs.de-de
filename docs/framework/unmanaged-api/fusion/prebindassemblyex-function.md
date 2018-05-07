---
title: PreBindAssemblyEx-Funktion
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d3e2535851d39be642de56a86b78c328ecaf446
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` ein null-Verweis muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `ppNamePostPolicy` Output-Parameter festgelegt ist, nur, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt. Es ist, andernfalls null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
