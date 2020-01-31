---
title: 'Processunprocessdexception-Funktion: Referenz zur nicht verwalteten WPF-API'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743919"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>Processunprocessdexception-Funktion (Referenz zur nicht verwalteten WPF-API)
Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Ausnahmebehandlung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>Parameters  
 ERRORMSG  
 Die Fehlermeldung.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 In den .NET Framework 3,0 und 3,5: presentationhostdll. dll  
  
 In den .NET Framework 4 und höher: PresentationHost_v0400. dll  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
