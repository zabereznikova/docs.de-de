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
ms.openlocfilehash: 8251d21fe535f85cc6abd0a7bc6c96ab320007f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090237"
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx-Funktion
Ruft den Anzeigenamen für die nach der Richtlinie für eine Assembly ab.  
  
 Diese Funktion unterstützt die .NET Framework-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pAppCtx`  
 [in] Gibt den Anwendungskontext.  
  
 `pName`  
 [in] Bezeichnet den Assemblynamen an.  
  
 `pAsmParent`  
 [in] Identifiziert die übergeordnete Assembly. Konvertiert die Zeichenfolgendarstellung einer Zahl in einem angegebenen Stil und einem kulturspezifischen Format in die entsprechende 32-Bit-Ganzzahl mit Vorzeichen.  
  
 `pwzRuntimeVersion`  
 [in] Identifiziert die Runtimeversion der Common Language.  
  
 `ppNamePostPolicy`  
 [out] Enthält den Anzeigenamen nach der Richtlinie an.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` ein null-Verweis muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt. Es ist, andernfalls null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
