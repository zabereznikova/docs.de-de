---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545341"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppenum`  
  
 [out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) Schnittstellenzeiger auf. Wenn die Methode fehlschlägt, ist der Wert dieser Variablen Ausgabe nicht definiert.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG und E_OUTOFMEMORY E_UNEXPECTED.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Methode ist es möglich, einen Punkt in der Enumerationsfolge zu erfassen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück. Der Aufrufer muss diesen neuen Enumerator separat aus dem ersten Enumerator freigeben.
