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
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921380"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Übergeben eines URI an die Windows-Runtime
Windows Runtime-Methoden akzeptieren nur absolute URIs. Wenn Sie einen relativen URI an eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Methode übergeben, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst. Erläuterung: Bei Verwendung der [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework-Code, der <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse angezeigt wird, als <xref:System.Uri?displayProperty=nameWithType> in Intellisense. Die <xref:System.Uri?displayProperty=nameWithType> -Klasse ermöglicht relative URIs, aber die <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse jedoch nicht. Dies gilt auch für Methoden, die Sie in [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten verfügbar machen. Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>. Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.  
  
In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Erkennen und Verwenden eines absoluten URIs  
Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an [!INCLUDE[wrt](../../../includes/wrt-md.md)] übergeben wird. Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Verwenden eines absoluten URI für eine Ressource im App-Paket  
Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.  
  
Das folgende Beispiel zeigt, wie Sie festlegen der <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.WebView> Steuerelement und die <xref:Windows.UI.Xaml.Controls.Image.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.Image> Steuerung auf Ressourcen, die in einem Ordner namens Seiten, die mit XAML und Code enthalten sind.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Weitere Informationen über diese Schemas finden Sie unter [URI-Schemas](/windows/uwp/app-resources/uri-schemes) im Windows Dev Center.  
  
## <a name="see-also"></a>Siehe auch

- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
