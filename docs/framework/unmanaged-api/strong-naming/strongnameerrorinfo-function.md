---
title: StrongNameErrorInfo-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e17ec04293f6274e307c66fc242c49bbdeee507
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo-Funktion
Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 Diese Funktion ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der letzte com-Fehlercode festlegen, indem eine der Funktionen mit starkem Namen.  
  
## <a name="remarks"></a>Hinweise  
 Die meisten Methoden mit starkem Namen zurückgeben ein einfachen `true` oder `false` Angabe der erfolgreichen Beendigung. Verwenden der `StrongNameErrorInfo` Funktion, um einen HRESULT-Wert abzurufen, der angibt, den letzten Fehler, die von Funktionen mit starkem Namen generiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Starke Namen von globalen statischen Funktionen](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
