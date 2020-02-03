---
title: 'Savetohistory-Funktion: Referenz zur nicht verwalteten WPF-API'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 7337e5dc23a3dce5de8270902bce228c49bc6edb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731748"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>Savetohistory-Funktion (Referenz zur nicht verwalteten WPF-API)
Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>Parameter  
 "phistorystream"  
 Ein Zeiger auf den Verlaufs Datenstrom.  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 In den .NET Framework 3,0 und 3,5: presentationhostdll. dll  
  
 In den .NET Framework 4 und höher: PresentationHost_v0400. dll  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
