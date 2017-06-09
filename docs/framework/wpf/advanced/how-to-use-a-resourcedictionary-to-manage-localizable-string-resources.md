---
title: "Gewusst wie: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary | Microsoft Docs"
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
  - "Lokalisierung [WPF], Verpacken von Zeichenfolgenressourcen"
  - "Verpacken von Zeichenfolgenressourcen"
  - "ResourceDictionary [WPF]"
  - "Ressourcen [WPF], Verpacken von Zeichenfolgenressourcen"
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.ResourceDictionary> zum Packen lokalisierbarer Zeichenfolgenressourcen für [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen verwendet wird.  
  
### So verwalten Sie lokalisierbare Zeichenfolgenressourcen mit einem ResourceDictionary  
  
1.  Erstellen Sie ein <xref:System.Windows.ResourceDictionary>, das die Zeichenfolgen enthält, die lokalisiert werden sollen.  Im Folgenden ein Codebeispiel.  
  
     [!code-xml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     In diesem Code wird eine Zeichenfolgenressource, `localizedMessage`, des Typs <xref:System.String> über den <xref:System>\-Namespace in mscorlib.dll definiert.  
  
2.  Fügen Sie das <xref:System.Windows.ResourceDictionary> mit folgendem Code zur Anwendung hinzu.  
  
     [!code-xml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Verwenden Sie die Markup\-Zeichenfolgenressource mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wie dem folgenden.  
  
     [!code-xml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Verwenden Sie die Code\-Behind\-Zeichenfolgenressource mit einem Code wie dem folgenden.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Lokalisieren Sie die Anwendung.  Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).