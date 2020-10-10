---
title: Prepareheaderdrag-Methode (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Erfahren Sie mehr über die private WPF-Methode mit dem Namen prepareheaderdrag.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877784"
---
# <a name="prepareheaderdrag-method"></a>Prepareheaderdrag-Methode

Bereitet den angegebenen Spaltenheader für die Neuanordnung vor.

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> Diese Methode ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="parameters"></a>Parameter

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
Der Spaltenheader, der für die Neuanordnung vorbereitet werden soll.

`pos` <xref:System.Windows.Point>\
Die Position relativ zu <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , an der der Zieh Vorgang beginnt.

`relativePos` <xref:System.Windows.Point>\
Die Position relativ zu `header` , an der der Zieh Vorgang beginnt.

`cancelInvoke` <xref:System.Boolean>\
`true` , wenn die Neuanordnung abgebrochen werden soll. andernfalls `false` .

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Windows.Controls>

**Assembly:** PresentationFramework.dll

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
