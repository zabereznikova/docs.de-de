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
ms.openlocfilehash: d5eedc34b75d3a0c02969c06454b0f7ec942ed17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176941"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo-Funktion
Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 Diese Funktion ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameErrorInfo ();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der letzte COM-Fehlercode, der durch eine der Funktionen mit starkem Namen festgelegt wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Die meisten der Methoden mit `true` `false` starkem Namen geben einen einfachen oder Hinweis auf einen erfolgreichen Abschluss zurück. Verwenden `StrongNameErrorInfo` Sie die Funktion, um ein HRESULT abzurufen, das den letzten Fehler angibt, der von den Funktionen des starken Namens generiert wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
