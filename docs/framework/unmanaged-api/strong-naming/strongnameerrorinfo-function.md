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
ms.openlocfilehash: 90abfcd573795ae529714e21b13f90d6e15c7dad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732267"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo-Funktion

Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 Diese Funktion ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameErrorInfo ();
```  
  
## <a name="return-value"></a>Rückgabewert  

 Der letzte com-Fehlercode, der von einer der Funktionen für starke Namen festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  

 Die meisten der Methoden für starke Namen geben eine `true` einfache `false` Angabe oder einen Hinweis auf einen erfolgreichen Abschluss zurück. Verwenden Sie die- `StrongNameErrorInfo` Funktion, um ein HRESULT abzurufen, das den letzten Fehler angibt, der von den Funktionen für starke Namen generiert wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
