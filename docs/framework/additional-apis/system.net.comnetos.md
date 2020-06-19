---
title: Comnettos-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990483"
---
# <a name="comnetos-class"></a>Comnettos-Klasse

Bietet Informationen zum aktuellen Betriebssystem, z. b. Version und Installationstyp (Client oder Server). Diese Klasse kann nicht vererbt werden.
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="iswin7orlater-field"></a>IsWin7orLater-Feld

Gibt an, ob die Betriebssystemversion Windows 7 oder höher ist.

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
