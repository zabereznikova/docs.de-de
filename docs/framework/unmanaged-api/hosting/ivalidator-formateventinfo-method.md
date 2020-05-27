---
title: IValidator::FormatEventInfo-Methode
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 0c60631b5e034bc46d74412440d35d526359d043
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008572"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo-Methode
Ruft die Fehlermeldung ab, die dem angegebenen Validierungs Fehler entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hVECode`  
 in Der HRESULT-Wert, der an den Validierungs Fehlerhandler übermittelt wurde.  
  
 `Context`  
 in Eine- `VEContext` Instanz, die Kontextinformationen über den Validierungs Fehler enthält.  
  
 `msg`  
 [in, out] Eine Zeichenfolge, die die zurückgegebene Fehlermeldung enthält.  
  
 `ulMaxLength`  
 in Die maximale Länge der Fehlermeldung.  
  
 `psa`  
 in Ein sicheres Array, das zusätzliche Parameter enthält, die den Fehler beschreiben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
