---
title: Übergeben eines URI an die Windows-Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5805c2c16cd23a18a0fe5bb587a3c106b307092f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423357"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Übergeben eines URI an die Windows-Runtime
Windows Runtime-Methoden akzeptieren nur absolute URIs. Wenn Sie einen relativen URI an eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Methode übergeben, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst. Erfahren Sie, warum: bei Verwendung der [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework-Code, der <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse angezeigt wird, als <xref:System.Uri?displayProperty=nameWithType> in Intellisense. Die <xref:System.Uri?displayProperty=nameWithType> -Klasse ermöglicht relative URIs, aber die <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse jedoch nicht. Dies gilt auch für Methoden, die Sie in [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten verfügbar machen. Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>. Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.  
  
 In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Erkennen und Verwenden eines absoluten URIs  
 Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an [!INCLUDE[wrt](../../../includes/wrt-md.md)] übergeben wird. Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Verwenden eines absoluten URI für eine Ressource im App-Paket  
 Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.  
  
 Das folgende Beispiel zeigt, wie Sie festlegen der [Quelle](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) -Eigenschaft für eine [WebView](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) Steuerelement und die [Quelle](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) -Eigenschaft für eine [Image](https://msdn.microsoft.com/library/windows/apps/br242752.aspx) Steuerelement auf Ressourcen, die in einem Ordner namens Seiten, die mit XAML und Code enthalten sind.  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Weitere Informationen über diese Schemas finden Sie unter [URI-Schemas](https://msdn.microsoft.com/library/windows/apps/jj655406.aspx) im Windows Dev Center.  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
