---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053421"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppenum`  
  
 vorgenommen Adresse der Ausgabevariablen, die den [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) -Schnittstellen Zeiger empfängt. Wenn die Methode nicht erfolgreich ist, ist der Wert dieser Ausgabevariablen nicht definiert.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Diese Methode unterstützt die Standard Rückgabewerte E_INVALIDARG, E_OUTOFMEMORY und E_UNEXPECTED.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ermöglicht es, einen Punkt in der enumerationssequenz aufzuzeichnen, um zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurückzukehren. Der Aufrufer muss diesen neuen Enumerator getrennt vom ersten Enumerator freigeben.
