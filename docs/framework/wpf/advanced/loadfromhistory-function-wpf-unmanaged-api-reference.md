---
title: 'Loadfromhistory-Funktion: Referenz zur nicht verwalteten WPF-API'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727931"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Loadfromhistory-Funktion (Referenz zur nicht verwalteten WPF-API)
Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parameters  
 "phistorystream"  
 Ein Zeiger auf einen Stream von Verlaufs Informationen.  
  
 pBindCtx  
 Ein Zeiger auf einen Bindungs Kontext.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 In den .NET Framework 3,0 und 3,5: presentationhostdll. dll  
  
 In den .NET Framework 4 und höher: PresentationHost_v0400. dll  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
