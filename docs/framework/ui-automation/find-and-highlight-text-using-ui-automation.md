---
title: "Find and Highlight Text Using UI Automation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "text, highlighting"
  - "finding text"
  - "text, finding"
  - "UI automation, highlighting text"
  - "UI automation, finding text"
  - "highlighting text"
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Find and Highlight Text Using UI Automation
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema veranschaulicht, wie jedes Vorkommen einer Zeichenfolge innerhalb eines Textes mithilfe von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sequenziell gesucht und hervorgehoben werden kann.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Automation.TextPattern>\-Objekt aus einem Textsteuerelement abgerufen.  Anschließend wird ein <xref:System.Windows.Automation.Text.TextPatternRange>\-Objekt, das den Textinhalt des gesamten Dokuments darstellt, mithilfe der <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> \-Eigenschaft des <xref:System.Windows.Automation.TextPattern> erstellt.  Zwei zusätzliche <xref:System.Windows.Automation.Text.TextPatternRange>\-Objekte werden dann für die sequenzielle Suche und das Hervorheben erstellt.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## Siehe auch  
 [Find and Highlight Text Using UI Automation](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)