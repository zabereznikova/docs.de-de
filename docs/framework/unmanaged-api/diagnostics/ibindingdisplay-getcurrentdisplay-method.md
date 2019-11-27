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
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448504"
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
 Die [IBindingDisplay:: InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) -Methode muss bereits erfolgreich sein, und das Programm muss von einem Debugger beendet werden.  
  
 Der Aufrufer muss den zurückgegebenen `SAFEARRAY` Speicher mithilfe von [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)nicht mehr zuordnen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Bindingdisplay. h  
  
 **Bibliothek:** Bindingdisplay. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IBindingDisplay-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [InitializeForProcess-Methode](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
