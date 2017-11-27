---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a>GetCustomUI
Wird vom PresentationHost.exe abzurufenden benutzerdefinierten Status- und Fehlermeldungen vom Host aufgerufen, wenn implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzProgressAssemblyName`  
  
 [out] Ein Zeiger auf die Assembly, die den Host bereitgestellte tasksequenzstatus-Benutzeroberfläche enthält.  
  
 `pwzProgressClassName`  
  
 [out] Der Name der Klasse, die den Host bereitgestellte tasksequenzstatus-Benutzeroberfläche, vorzugsweise ist ein [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] -Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die von angegeben wird `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Ein Zeiger auf die Assembly, die Fehler Host bereitgestellte Benutzeroberfläche enthält.  
  
 `pwzErrorClassName`  
  
 [out] Der Name der Klasse, die der Host angegebene Benutzer ist Schnittstelle vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die von angegeben wird `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung möglicherweise ein bestimmtes Design, dem nicht PresentationHost.exe des standardmäßigen Benutzeroberflächen entsprechen können. Wenn dies der Fall ist, kann die hostanwendung implementieren [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) Status- und Fehlerinformationen von Benutzeroberflächen für PresentationHost.exe zurückgegeben. Rufen Sie PresentationHost.exe wird immer [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) vor der Verwendung der standardmäßigen Benutzeroberflächen.  
  
 Diese Funktion wird einmal während der Initialisierung von PresentationHost aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
