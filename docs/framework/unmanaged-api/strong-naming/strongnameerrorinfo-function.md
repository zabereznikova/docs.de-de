---
title: StrongNameErrorInfo-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a905840c471a268c6b106c5e25baca9c36f485d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731061"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo-Funktion
Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 Diese Funktion wurde als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der letzte com-Fehlercode von einer der Funktionen mit starkem Namen festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die meisten Methoden mit starkem Namen zurückgeben, eine einfache `true` oder `false` Angabe für die erfolgreiche Ausführung. Verwenden der `StrongNameErrorInfo` Funktion, die einen HRESULT-Wert abzurufen, der angibt, den letzten Fehler, die von Funktionen mit starkem Namen generiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Globale statische Funktionen für starke Namen](https://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
