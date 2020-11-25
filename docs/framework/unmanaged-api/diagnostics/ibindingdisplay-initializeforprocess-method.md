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
ms.openlocfilehash: f9e65b49c9a3b506cba3493d81a40f2759dca781
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725145"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess-Methode

Initialisiert das [IBindingDisplay](ibindingdisplay-interface.md) -Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pid`  
 in Der Prozess Bezeichner.  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger ruft die- `InitializeForProcess` Methode zum Erstellungs Zeitpunkt auf, um die Bindungs Anzeige zu initialisieren. `InitializeForProcess` muss zur Erstellungszeit aufgerufen werden, bevor eine andere Methode für `IBindingDisplay` aufgerufen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Bindingdisplay. h  
  
 **Bibliothek:** Bindingdisplay. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IBindingDisplay-Schnittstelle](ibindingdisplay-interface.md)
