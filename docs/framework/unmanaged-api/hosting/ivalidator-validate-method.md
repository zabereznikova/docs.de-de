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
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699143"
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
 in Ein Zeiger auf eine- `IVEHandler` Instanz, die Validierungs Fehler behandelt.  
  
 `pAppDomain`  
 in Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.  
  
 `ulFlags`  
 in Eine bitweise Kombination von [ValidatorFlags](validatorflags-enumeration.md) -Werten, die die auszuführenden Validierungen angeben.  
  
 `ulMaxError`  
 in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.  
  
 `token`  
 [in] Wird nicht verwendet.  
  
 `fileName`  
 in Eine Zeichenfolge, die den Namen der zu validierenden Datei angibt.  
  
 `pe`  
 in Ein Zeiger auf den Speicherpuffer, in dem die Datei gespeichert ist.  
  
 `ulSize`  
 in Die Größe (in Bytes) der zu validierenden Datei.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
