---
title: "GetCustomUI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Benutzerdefinierte Fehlermeldungen [WPF]"
  - "GetCustomUI-Methode"
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# GetCustomUI
Von PresentationHost.exe aufgerufen, um benutzerdefinierte Fortschritts\- und Fehlermeldungen vom Host abzurufen, sofern implementiert.  
  
## Syntax  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### Parameter  
 `pwzProgressAssemblyName`  
  
 \[out\] Ein Zeiger auf die Assembly, die die vom Host angegebene Fortschrittsbenutzeroberfläche enthält.  
  
 `pwzProgressClassName`  
  
 \[out\] Der Name der Klasse, die die vom Host angegebene Fortschrittsbenutzeroberfläche darstellt, vorzugsweise eine [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Datei mit <xref:System.Windows.Controls.Page> als Element der obersten Ebene.  Diese Klasse befindet sich in der Assembly, die von `pwzProgressAssemblyName` angegeben wird.  
  
 `pwzErrorAssemblyName`  
  
 \[out\] Ein Zeiger auf die Assembly, die die vom Host angegebene Fehlerbenutzeroberfläche enthält.  
  
 `pwzErrorClassName`  
  
 \[out\] Der Name der Klasse, die die vom Host angegebene Fehlerbenutzeroberfläche darstellt, vorzugsweise eine XAML\-Datei mit <xref:System.Windows.Controls.Page> als Element der obersten Ebene.  Diese Klasse befindet sich in der Assembly, die von `pwzErrorAssemblyName` angegeben wird.  
  
## Eigenschaftswert\/Rückgabewert  
 HRESULT: Ignoriert.  
  
## Hinweise  
 Eine Hostanwendung weist möglicherweise ein bestimmtes Design auf, dem die Standardbenutzeroberflächen von PresentationHost.exe unter Umständen nicht entsprechen.  In diesem Fall kann die Hostanwendung [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) implementieren, um Fortschritts\- und Fehlerbenutzeroberflächen an PresentationHost.exe zurückzugeben.  PresentationHost.exe ruft vor Verwendung der eigenen Standardbenutzeroberflächen immer [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) auf.  
  
 Diese Funktion wird einmal während der Initialisierung von PresentationHost aufgerufen.  
  
## Siehe auch  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)