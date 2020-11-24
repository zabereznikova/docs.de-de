---
title: CreateICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 454cfa2dd1b676f32649050625b1074fbd776d54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673331"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen-Funktion

Erstellt ein [ICeeFileGen](iceefilegen-class.md) -Objekt.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ceeFileGen`  
 vorgenommen Ein Zeiger auf die Adresse eines neuen- `ICeeFileGen` Objekts.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt com-Standard Fehlercodes zurück.  
  
## <a name="remarks"></a>Hinweise  

 Das- `ICeeFileGen` Objekt wird verwendet, um Common Language Runtime (CLR) portable ausführbare Dateien (PE) zu erstellen.  
  
 Nennen Sie die [DestroyICeeFileGen](destroyiceefilegen-function.md) -Funktion, um das Objekt zu zerstören, `ICeeFileGen` Wenn es beendet wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** ICeeFileGen. h  
  
 **Bibliothek:** MSCorPE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
