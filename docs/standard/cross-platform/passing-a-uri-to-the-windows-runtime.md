---
title: "&#220;bergeben eines URI an die Windows-Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Windows-Runtime, .NET Framework-Unterstützung für"
  - "Windows-Runtime, Übergeben eines URI an"
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bergeben eines URI an die Windows-Runtime
Windows Runtime\-Methoden akzeptieren nur absolute URIs. Wenn Sie einen relativen URI an eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]\-Methode übergeben, wird eine <xref:System.ArgumentException>\-Ausnahme ausgelöst. Erläuterung: Wenn Sie das [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework\-Code verwenden, wird die [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376)\-Klasse als <xref:System.Uri?displayProperty=fullName> in IntelliSense angezeigt. Die <xref:System.Uri?displayProperty=fullName>\-Klasse erlaubt relative URIs, die [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376)\-Klasse jedoch nicht. Dies gilt auch für Methoden, die Sie in [!INCLUDE[wrt](../../../includes/wrt-md.md)]\-Komponenten verfügbar machen. Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=fullName>. Für Benutzer Ihrer Komponente enthält die Signatur jedoch [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376). Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.  
  
 In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App\-Paket verweisen.  
  
## Erkennen und Verwenden eines absoluten URIs  
 Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=fullName>\-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an [!INCLUDE[wrt](../../../includes/wrt-md.md)] übergeben wird. Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>\-Ausnahme.  
  
## Verwenden eines absoluten URI für eine Ressource im App\-Paket  
 Wenn Sie einen URI für eine Ressource angeben möchten, der im App\-Paket enthalten sein soll, können Sie das `ms-appx`\-Schema oder `ms-appx-web`\-Schema verwenden, um einen absoluten URI zu erstellen.  
  
 Das folgende Beispiel zeigt, wie die [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx)\-Eigenschaft für ein [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx)\-Steuerelement und die [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx)\-Eigenschaft für ein [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx)\-Steuerelement unter Verwendung von XAML und Code auf Ressourcen festgelegt werden, die in einem Ordner mit dem Namen „Pages“ enthalten sind.  
  
 [!code-xml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Weitere Informationen über diese Schemas finden Sie unter [URI\-Schemas](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) im Windows Developer Center.  
  
## Siehe auch  
 [.NET Framework\-Unterstützung für Windows Store\-Apps und Windows\-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)