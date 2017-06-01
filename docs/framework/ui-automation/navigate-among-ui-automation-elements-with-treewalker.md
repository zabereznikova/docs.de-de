---
title: "Navigate Among UI Automation Elements with TreeWalker | Microsoft Docs"
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
  - "classes, TreeWalker"
  - "TreeWalker class"
  - "elements, navigating among"
  - "UI Automation, navigating among elements"
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
caps.latest.revision: 8
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 8
---
# Navigate Among UI Automation Elements with TreeWalker
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode zur Veranschaulichung der Navigation zwischen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]\-Elementen unter Verwendung der <xref:System.Windows.Automation.TreeWalker>\-Klasse.  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetParent%2A> verwendet, um die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]\-Struktur in Aufwärtsrichtung bis zum Stammelement bzw. dem Desktop zu durchsuchen.  Bei dem Element direkt darunter handelt es sich um das übergeordnete Fenster des angegebenen Elements.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> und <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> zum Erstellen eines <xref:System.Windows.Forms.TreeView> verwendet, von der die gesamte Unterstruktur der in der Steuerelementansicht aktivierten [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]\-Elemente angezeigt wird.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## Siehe auch  
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)