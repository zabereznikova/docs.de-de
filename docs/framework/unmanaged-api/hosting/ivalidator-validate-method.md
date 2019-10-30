---
title: IValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123270"
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate-Methode
Überprüft die angegebene PE-Datei (portable ausführbare Datei) oder die MSIL-Datei (Microsoft Intermediate Language).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `veh`  
 in Ein Zeiger auf eine `IVEHandler`-Instanz, die Validierungs Fehler behandelt.  
  
 `pAppDomain`  
 in Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.  
  
 `ulFlags`  
 in Eine bitweise Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) -Werten, die die auszuführenden Validierungen angeben.  
  
 `ulMaxError`  
 in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.  
  
 `token`  
 in Nicht verwendet.  
  
 `fileName`  
 in Eine Zeichenfolge, die den Namen der zu validierenden Datei angibt.  
  
 `pe`  
 in Ein Zeiger auf den Speicherpuffer, in dem die Datei gespeichert ist.  
  
 `ulSize`  
 in Die Größe (in Bytes) der zu validierenden Datei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
