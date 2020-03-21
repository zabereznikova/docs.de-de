---
title: CreateIDispatchSTAForwarder-Funktion - Nicht verwalteter WPF-API-Verweis
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174718"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder-Funktion (WPF-Referenz für nicht verwaltete API)
Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und ist nicht für die direkte Verwendung aus ihrem Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Thread- und Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parameter  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 pDispatchDelegate  
 Ein Zeiger auf `IDispatch` eine Schnittstelle.  
  
 ppForwarder  
 Ein Zeiger auf die `IDispatch` Adresse einer Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Siehe [.NET Framework Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 und höher: PresentationHost_v0400.dll  
  
 **.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
