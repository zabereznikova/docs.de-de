---
title: LoadFromHistory-Funktion - Nicht verwalteter WPF-API-Verweis
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141574"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory-Funktion (WPF-Referenz für nicht verwaltete API)
Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und ist nicht für die direkte Verwendung aus ihrem Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parameter  
 pHistoryStream  
 Ein Zeiger auf einen Strom von Verlaufsinformationen.  
  
 pBindCtx  
 Ein Zeiger auf einen Bindungskontext.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Siehe [.NET Framework Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 und höher: PresentationHost_v0400.dll  
  
 **.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
