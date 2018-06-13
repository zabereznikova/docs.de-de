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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 875052ed26e83de50807e33e9c74dcf89f7ee679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440644"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo-Methode
Ruft die Fehlermeldung, die entsprechend des angegebenen Validierungsfehlers ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hVECode`  
 [in] Der HRESULT-Wert, der an den Fehlerhandler Überprüfung übergeben wurde.  
  
 `Context`  
 [in] Ein `VEContext` -Instanz, die Kontextinformationen zum valdierungsfehler enthält.  
  
 `msg`  
 [in, out] Eine Zeichenfolge, die die zurückgegebene Fehlermeldung enthält.  
  
 `ulMaxLength`  
 [in] Die maximale Länge der Fehlermeldung.  
  
 `psa`  
 [in] Ein sicheres Array, das zusätzliche Parameter, die Beschreibung des Fehlers enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
