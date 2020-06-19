---
title: ServicePointManager. closeconnectiongroups-Methode (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990449"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a>ServicePointManager. closeconnectiongroups-Methode

Durchläuft alle Dienst Punkte und schließt Verbindungs Gruppen mit dem angegebenen Namen.

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> Diese Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="parameters"></a>Parameter

`connectionGroupName` <xref:System.String>

Der Name der Verbindungsgruppe, die geschlossen werden soll.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
