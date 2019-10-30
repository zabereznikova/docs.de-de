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
ms.openlocfilehash: db3ba3380d1fc30a8f34683618b5cc326d7d1906
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123056"
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx-Funktion
Ruft den anzeigen Amen für eine Assembly nach der Richtlinie ab.  
  
 Diese Funktion unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Identifiziert den Anwendungskontext.  
  
 `pName`  
 in Identifiziert den Assemblynamen.  
  
 `pAsmParent`  
 in Identifiziert die übergeordnete Assembly. Konvertiert die Zeichenfolgendarstellung einer Zahl in einem angegebenen Stil und einem kulturspezifischen Format in die entsprechende 32-Bit-Ganzzahl mit Vorzeichen.  
  
 `pwzRuntimeVersion`  
 in Identifiziert die Laufzeitversion.  
  
 `ppNamePostPolicy`  
 vorgenommen Enthält den anzeigen Amen nach der Richtlinie.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` muss ein NULL-Verweis sein.  
  
## <a name="remarks"></a>Hinweise  
 Der `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt. Andernfalls ist der Wert NULL.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
