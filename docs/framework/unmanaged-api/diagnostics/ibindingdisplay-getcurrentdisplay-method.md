---
title: IBindingDisplay::GetCurrentDisplay-Methode
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: d52f089923d16f93345444c07ff8e0619644f2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725152"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>IBindingDisplay::GetCurrentDisplay-Methode

Gibt die aktuellen Bindungs Anzeigeinformationen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `display`  
 [out, retval] Ein Zeiger auf ein SafeArray, das die Informationen zur Bindungs Anzeige enthält.  
  
## <a name="remarks"></a>Hinweise  

 Die [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) -Methode muss bereits erfolgreich sein, und das Programm muss von einem Debugger beendet werden.  
  
 Der Aufrufer muss den zurückgegebenen `SAFEARRAY` Speicher mithilfe von [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)zurücksetzen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Bindingdisplay. h  
  
 **Bibliothek:** Bindingdisplay. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IBindingDisplay-Schnittstelle](ibindingdisplay-interface.md)
- [InitializeForProcess-Methode](ibindingdisplay-initializeforprocess-method.md)
