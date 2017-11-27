---
title: CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63195ce2a47add2606f528b18d0d1d58ab0d968c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)
Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.  
  
 Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Threads und Windows.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a>Parameter  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 pDispatchDelegate  
 Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
 ppForwarder  
 Ein Zeiger auf die Adresse einer `IDispatch` Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 und höher: PresentationHost_v0400.dll  
  
 **.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [WPF – Referenz zur nicht verwalteten API](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
