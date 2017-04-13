---
title: "Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen | Microsoft Docs"
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
  - "Anwendungen, Lokalisierbar"
  - "Lokalisierbare Anwendungen"
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen
Lokalisierung bedeutet, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für andere Länder anzupassen.  Dazu müssen Texte wie Titel, Beschriftungen, Elemente in Listenfeldern usw. übersetzt werden.  Damit dies leichter gelingt, werden die zu übersetzenden Elemente in Ressourcendateien gesammelt.  Informationen über das Erstellen einer Ressourcendatei für die Lokalisierung finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  Wenn eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung lokalisierbar sein soll, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen.  Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code\-Behind wird mithilfe der Ressourcenverwaltungs\-[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen.  Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ist eine Projektdatei \(.proj\).  Alle in der Anwendung verwendeten Ressourcen müssen in der Projektdatei enthalten sein.  Dies wird im folgenden Codebeispiel verdeutlicht.  
  
## Beispiel  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Um eine Ressource in der Anwendung zu verwenden, instanziieren Sie <xref:System.Resources.ResourceManager>, und laden Sie die zu verwendende Ressource.  Im folgenden Beispiel wird veranschaulicht, wie Sie dafür vorgehen müssen.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]