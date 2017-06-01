---
title: "Add Content to a Text Box Using UI Automation | Microsoft Docs"
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
  - "adding content to text boxes"
  - "text boxes, adding content"
  - "UI Automation, adding content to text boxes"
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Add Content to a Text Box Using UI Automation
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der die Verwendung von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Einfügen von Text in ein einzeiliges Textfeld veranschaulicht.  Für mehrzeilige und Rich\-Text\-Steuerelemente, bei denen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] nicht anwendbar ist, steht eine alternative Methode zur Verfügung.  Zum Vergleich wird in diesem Beispiel ebenfalls gezeigt, wie die gleichen Ergebnisse mit Win32\-Methoden erzielt werden können.  
  
## Beispiel  
 Im folgenden Beispiel wird in einer Zielanwendung eine Reihe von Textsteuerelementen durchlaufen.  Jedes Textsteuerelement wird getestet, um zu ermitteln, ob aus dem Steuerelement ein <xref:System.Windows.Automation.ValuePattern>\-Objekt mit der <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>\-Methode abgerufen werden kann.  Wenn das Textsteuerelement <xref:System.Windows.Automation.ValuePattern> unterstützt, wird die <xref:System.Windows.Automation.ValuePattern.SetValue%2A>\-Methode verwendet, um eine benutzerdefinierte Zeichenfolge in das Textsteuerelement einzufügen.  Andernfalls wird die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=fullName>\-Methode verwendet.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## Siehe auch  
 [TextPattern Insert Text Sample](http://msdn.microsoft.com/de-de/67353f93-7ee2-42f2-ab76-5c078cf6ca16)