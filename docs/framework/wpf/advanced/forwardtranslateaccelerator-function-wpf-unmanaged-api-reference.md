---
title: 'Forwardtranslateaccelerator-Funktion: Referenz zur nicht verwalteten WPF-API'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747040"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Forwardtranslateaccelerator-Funktion (Referenz zur nicht verwalteten WPF-API)
Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parameters  
 pmsg  
 Ein Zeiger auf eine Meldung.  
  
 appunbehandelte  
 `true`, wenn der App bereits die Möglichkeit gegeben wurde, die Eingabe Nachricht zu verarbeiten, Sie aber nicht behandelt hat. Andernfalls `false`.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 In den .NET Framework 3,0 und 3,5: presentationhostdll. dll  
  
 In den .NET Framework 4 und höher: PresentationHost_v0400. dll  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
