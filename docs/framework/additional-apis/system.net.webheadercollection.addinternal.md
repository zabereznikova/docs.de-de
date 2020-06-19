---
title: WebHeaderCollection. addinternal-Methode (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990446"
---
# <a name="webheadercollectionaddinternal-method"></a>WebHeaderCollection. addinternal-Methode

Fügt der Auflistung einen neuen Header mit dem angegebenen Namen und Wert hinzu, wobei die Überprüfungen umgangen werden.

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> Diese Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="parameters"></a>Parameter

- `name` <xref:System.String>

  Der Name des Headers.

- `value` <xref:System.String>

  Der Wert des Headers.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
