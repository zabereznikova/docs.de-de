---
title: IBindingDisplay::InitializeForProcess-Methode
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775947"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess-Methode
Initialisiert die [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pid`  
 [in] Die Prozess-ID.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger Ruft die `InitializeForProcess` Methode zum Zeitpunkt der Erstellung die Bindungsanzeige zu initialisieren. `InitializeForProcess` muss zum Zeitpunkt der Erstellung vor jeder anderen Methode aufgerufen werden, für `IBindingDisplay` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** BindingDisplay.h  
  
 **Bibliothek:** BindingDisplay.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IBindingDisplay-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
