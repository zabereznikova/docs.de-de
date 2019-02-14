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
ms.openlocfilehash: b3d7555ec5b87957ff1c8e085a4c3ac44c660b0c
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260815"
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
  
