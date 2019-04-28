---
title: Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777168"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)

Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.

Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.

## <a name="syntax"></a>Syntax

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parameter

`pParameters`\
Ein Zeiger auf die Aktivierungsparameter des Fensters.

`ppInner`\
Ein Zeiger auf die Adresse eines Puffers, der einen Zeiger auf enthält einem Element eine <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).

**DLL:**

In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll

In .NET Framework 4 und höher: PresentationHost_v0400.dll

**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
