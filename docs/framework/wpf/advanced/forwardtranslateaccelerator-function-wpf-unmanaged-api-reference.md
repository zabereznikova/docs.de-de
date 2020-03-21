---
title: ForwardTranslateAccelerator-Funktion - Nicht verwalteter WPF-API-Verweis
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186633"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator-Funktion (WPF-Referenz für nicht verwaltete API)
Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und ist nicht für die direkte Verwendung aus ihrem Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parameter  
 pMsg  
 Ein Zeiger auf eine Nachricht.  
  
 appUnhandled  
 `true`wenn der App bereits die Möglichkeit gegeben wurde, die Eingabenachricht zu verarbeiten, sie jedoch nicht behandelt wurde. andernfalls `false`.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Siehe [.NET Framework Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 und höher: PresentationHost_v0400.dll  
  
 **.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
