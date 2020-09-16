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
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541707"
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
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Bindingdisplay. h  
  
 **Bibliothek:** Bindingdisplay. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IBindingDisplay-Schnittstelle](ibindingdisplay-interface.md)
- [InitializeForProcess-Methode](ibindingdisplay-initializeforprocess-method.md)
