---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949590"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppenum`  
  
 [out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) Schnittstellenzeiger auf. Wenn die Methode fehlschlägt, ist der Wert, der diese Output-Variable nicht definiert.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG, E_UNEXPECTED und E_OUTOFMEMORY.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ermöglicht es, einen Punkt in der Enumerationsfolge aufzeichnen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück. Der Aufrufer muss dieses neuen Enumerator getrennt von der erste Enumerator freigeben.
