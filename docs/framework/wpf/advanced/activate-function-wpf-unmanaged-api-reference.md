---
title: Aktivieren der Funktion-WPF-Referenz zur nicht verwalteten API
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734509"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Funktion aktivieren (Referenz zur nicht verwalteten WPF-API)

Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.

Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.

## <a name="syntax"></a>Syntax

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parameters

`pParameters`\
Ein Zeiger auf die Aktivierungs Parameter des Fensters.

`ppInner`\
Ein Zeiger auf die Adresse eines Einzelelement Puffers, der einen Zeiger auf ein <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt enthält.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).

**DLL**

In den .NET Framework 3,0 und 3,5: presentationhostdll. dll

In den .NET Framework 4 und höher: PresentationHost_v0400. dll

**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
