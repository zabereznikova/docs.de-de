---
title: Funktion "kreateidispatchstaforwarder"-Referenz zur nicht verwalteten WPF-API
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738029"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Funktion "kreateidispatchstaforwarder" (Referenz zur nicht verwalteten WPF-API)
Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Thread-und Windows-Verwaltung verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parameters  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 pdispatchdelegat  
 Ein Zeiger auf eine `IDispatch`-Schnittstelle.  
  
 ppforwarder  
 Ein Zeiger auf die Adresse einer `IDispatch`-Schnittstelle.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 In den .NET Framework 3,0 und 3,5: presentationhostdll. dll  
  
 In den .NET Framework 4 und höher: PresentationHost_v0400. dll  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WPF – Referenz zur nicht verwalteten API](wpf-unmanaged-api-reference.md)
