---
title: "Gewusst wie: Verwenden von Sonderzeichen in XAML | Microsoft Docs"
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
  - "Zeichen, Besondere"
  - "Sonderzeichen"
  - "Typografie, Sonderzeichen"
  - "Unicode UTF-8-Dateiformat"
  - "UTF-8-Dateiformat"
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Gewusst wie: Verwenden von Sonderzeichen in XAML
Markupdateien, die in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] erstellt werden, werden automatisch im Dateiformat [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]\-UTF\-8 gespeichert. Auf diese Weise werden die meisten Sonderzeichen, z. B. Akzentzeichen, richtig codiert.  Es gibt jedoch einige häufig verwendete Sonderzeichen, die anders behandelt werden.  Diese Sonderzeichen basieren auf dem [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)]\-[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Codierungsstandard.  
  
 Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:  
  
|Zeichen|Syntax|Beschreibung|  
|-------------|------------|------------------|  
|\<|`<`|Kleiner als\-Symbol|  
|\>|`>`|Größer als\-Symbol|  
|&|`&`|Kaufmännisches Und|  
|"|`"`|Doppeltes Anführungszeichen|  
  
> [!NOTE]
>  Wenn Sie mithilfe eines Texteditors eine Markupdatei erstellen, z. B. mit dem Editor von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], müssen Sie die Datei im Dateiformat [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]\-UTF\-8 speichern, um die codierten Sonderzeichen beizubehalten.  
  
 Das folgende Beispiel zeigt, wie Sie beim Erstellen von Markup Sonderzeichen im Text verwenden können.  
  
## Beispiel  
 [!code-xml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]