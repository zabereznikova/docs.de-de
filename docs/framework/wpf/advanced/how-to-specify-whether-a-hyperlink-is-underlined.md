---
title: "Gewusst wie: Angeben, ob ein Hyperlink unterstrichen wird | Microsoft Docs"
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
  - "Klassen, TextDecoration"
  - "HyperLink-Steuerelementtyp"
  - "TextDecoration-Klasse"
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Angeben, ob ein Hyperlink unterstrichen wird
Das <xref:System.Windows.Documents.Hyperlink>\-Objekt stellt ein fortlaufendes Inhaltselement auf Inlineebene dar, das Ihnen das Hosten von Links im fortlaufenden Inhalt ermöglicht.  Standardmäßig verwendet <xref:System.Windows.Documents.Hyperlink> ein <xref:System.Windows.TextDecoration>\-Objekt, um eine Unterstreichung anzuzeigen.  Die Instanziierung von <xref:System.Windows.TextDecoration>\-Objekten kann ressourcenintensiv sein, insbesondere bei vielen <xref:System.Windows.Documents.Hyperlink>\-Objekten.  Wenn Sie <xref:System.Windows.Documents.Hyperlink>\-Elemente häufig einsetzen, sollten Sie einen Unterstrich nur anzeigen, wenn Sie ein Ereignis, z. B. das <xref:System.Windows.ContentElement.MouseEnter>\-Ereignis, auslösen.  
  
 Im folgenden Beispiel ist der Unterstrich für den Link "My MSN" dynamisch. Er wird nur angezeigt, wenn das <xref:System.Windows.ContentElement.MouseEnter>\-Ereignis ausgelöst wird.  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Mit Textdekorationen definierte Links  
  
## Beispiel  
 Im folgenden Markupbeispiel wird ein <xref:System.Windows.Documents.Hyperlink> mit und ohne Unterstreichung definiert:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Im folgenden Beispiel wird das Erstellen einer Unterstreichung für den <xref:System.Windows.Documents.Hyperlink> bei Eintreten des <xref:System.Windows.ContentElement.MouseEnter>\-Ereignisses und das Entfernen dieser Unterstreichung bei Eintreten des <xref:System.Windows.ContentElement.MouseLeave>\-Ereignisses veranschaulicht.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## Siehe auch  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Erstellen einer Textdekoration](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)