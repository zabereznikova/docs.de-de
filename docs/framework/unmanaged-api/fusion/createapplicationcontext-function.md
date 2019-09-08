---
title: CreateApplicationContext-Funktion
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25364330dafdf858c4b41e9a05731c37e97fbb57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795434"
---
# <a name="createapplicationcontext-function"></a>CreateApplicationContext-Funktion
Diese Funktion unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `pName`  
 in Ein Zeiger auf einen anzeigen Amen.  
  
 `ppCtx`  
 vorgenommen Ein Zeiger auf einen Anwendungskontext.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** Als Ressource in Fusion. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyCache-Schnittstelle](iassemblycache-interface.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
