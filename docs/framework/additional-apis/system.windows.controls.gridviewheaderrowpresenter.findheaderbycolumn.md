---
title: Findheaderbycolumn-Methode (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Erfahren Sie mehr über die private WPF-Methode namens "findheaderbycolumn".
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877789"
---
# <a name="findheaderbycolumn-method"></a>Findheaderbycolumn-Methode

Sucht den Spaltenheader für die angegebene Spalte in der visuellen Struktur.

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> Diese Methode ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="parameters"></a>Parameter

`column` <xref:System.Windows.Controls.GridViewColumn>\
Die Spalte, deren Header gefunden und zurückgegeben werden soll.

## <a name="return-value"></a>Rückgabewert

<xref:System.Windows.Controls.GridViewColumnHeader>\
Der Header der angegebenen Spalte oder, `null` Wenn die angegebene Spalte nicht vorhanden ist.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Windows.Controls>

**Assembly:** PresentationFramework.dll

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
